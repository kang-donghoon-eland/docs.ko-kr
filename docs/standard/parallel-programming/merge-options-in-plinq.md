---
title: "Merge Options in PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, merge options"
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Merge Options in PLINQ
쿼리를 병렬로 실행할 때 PLINQ에서는 여러 스레드가 서로 다른 부분\(일반적으로 개별 스레드\)에서 작업을 수행할 수 있도록 소스 시퀀스를 분할합니다.  예를 들어 `foreach`\([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `For Each`\) 루프에서 결과가 한 스레드에 사용될 경우에는 모든 스레드의 결과를 다시 한 시퀀스에 병합해야 합니다.  PLINQ에서 수행되는 병합의 종류는 쿼리에 있는 연산자에 따라 달라집니다.  예를 들어 결과에 새 순서를 적용하는 연산자는 모든 스레드의 모든 요소를 버퍼링해야 합니다.  소비 스레드의 관점\(또한 응용 프로그램 사용자의 관점\)에서 완전히 버퍼링되는 쿼리는 첫 번째 결과를 생성하기까지 상당 시간 동안 실행되는 것으로 보일 수 있습니다.  다른 연산자는 기본적으로 버퍼링이 부분적으로 수행되며 결과를 일괄 처리로 생성합니다.  <xref:System.Linq.ParallelEnumerable.ForAll%2A> 연산자만 기본적으로 버퍼링되지 않습니다.  이 연산자는 모든 스레드에서 모든 요소를 즉시 생성합니다.  
  
 다음 예제에서처럼 <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> 메서드를 사용하면 수행할 병합 종류를 나타내는 힌트를 PLINQ에 제공할 수 있습니다.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 전체 예제를 보려면 [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)을 참조하십시오.  
  
 특정 쿼리에서 요청된 옵션을 지원할 수 없는 경우 해당 옵션은 무시됩니다.  대개는 PLINQ 쿼리에 대한 병합 옵션을 지정할 필요가 없습니다.  그러나 일부 경우에는 테스트와 측정을 통해 쿼리가 기본 모드가 아닌 모드에서 최적으로 실행됨을 확인하게 될 수도 있습니다.  병합 옵션은 일반적으로 응답성이 뛰어난 사용자 인터페이스를 제공하기 위해 청크 병합 연산자를 통해 해당 결과를 스트리밍하는 데 사용합니다.  
  
## ParallelMergeOptions  
 <xref:System.Linq.ParallelMergeOptions> 열거형에는 결과가 한 스레드에서 사용될 때 쿼리의 최종 출력이 생성되는 방식\(지원되는 쿼리 형태의 경우\)을 지정하는 다음 옵션이 포함되어 있습니다.  
  
-   `Not Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions> 옵션을 사용하면 처리된 각 요소는 각 스레드에서 생성되는 즉시 반환됩니다.  이 동작은 출력을 "스트리밍"하는 것과 유사합니다.  <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자가 쿼리에 있는 경우 `NotBuffered`를 사용하면 소스 요소의 순서가 유지됩니다.  `NotBuffered`는 결과를 사용할 수 있게 되는 즉시 생성하기 시작하지만 모든 결과를 생성하는 데 소요되는 총 시간은 다른 병합 옵션 중 하나를 사용할 때보다 깁니다.  
  
-   `Auto Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions> 옵션은 요소들을 버퍼에 담아달라는 쿼리를 야기시킨 다음 버퍼 내용을 모두 한꺼번에 소비 스레드로 내보냅니다.  이 방법은 `NotBuffered`의 "스트리밍" 동작을 사용하는 대신 "청크"에 소스 데이터를 생성하는 것과 유사합니다.  소비 스레드에서 첫 번째 요소를 사용할 수 있게 되는 시간은 `NotBuffered`의 경우보다 `AutoBuffered`의 경우가 더 길 수 있습니다.  버퍼 크기와 정확한 생성 동작은 구성할 수 없으며 쿼리와 관련된 다양한 요인에 다라 달라질 수 있습니다.  
  
-   `FullyBuffered`  
  
     <xref:System.Linq.ParallelMergeOptions> 옵션을 사용하면 요소가 생성되기 전에 전체 쿼리의 출력이 버퍼링됩니다.  이 옵션을 사용할 경우 소비 스레드에서 첫 번째 요소를 사용할 수 있게 될 때까지 시간이 오래 걸릴 수 있지만 전체 결과는 다른 옵션을 사용할 때보다 빠르게 생성할 수 있습니다.  
  
## 병합 옵션을 지원하는 쿼리 연산자  
 다음 표에서는 지정된 제한 사항에 따라 모든 병합 옵션 모드를 지원하는 연산자를 보여 줍니다.  
  
|연산자|제한|  
|---------|--------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|배열 또는 목록 소스만 있는 순서가 지정되지 않은 쿼리|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|배열 또는 목록 소스만 있는 순서가 지정되지 않은 쿼리|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|없음|  
  
 다른 모든 PLINQ 쿼리 연산자는 사용자가 제공한 병합 옵션을 무시할 수 있습니다.  예를 들어 <xref:System.Linq.ParallelEnumerable.Reverse%2A> 및 <xref:System.Linq.ParallelEnumerable.OrderBy%2A> 등의 일부 쿼리 연산자는 모든 요소가 생성되고 다시 정렬될 때까지 요소를 내보낼 수 없습니다.  따라서 <xref:System.Linq.ParallelEnumerable.Reverse%2A>와 같은 연산자도 포함된 쿼리에 <xref:System.Linq.ParallelMergeOptions>를 사용할 경우 해당 연산자가 결과를 생성할 때까지 병합 동작이 쿼리에 적용되지 않습니다.  
  
 일부 연산자는 소스 시퀀스의 형식과 쿼리의 앞부분에 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자가 사용되었는지 여부에 따라 병합 옵션의 처리 가능 여부가 달라집니다.  <xref:System.Linq.ParallelEnumerable.ForAll%2A>은 항상 <xref:System.Linq.ParallelMergeOptions>이며 해당 요소를 즉시 생성합니다.  <xref:System.Linq.ParallelEnumerable.OrderBy%2A>는 항상 <xref:System.Linq.ParallelMergeOptions>이며 목록을 생성하기 전에 전체 목록을 정렬해야 합니다.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)