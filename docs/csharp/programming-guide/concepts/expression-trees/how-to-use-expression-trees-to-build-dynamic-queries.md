---
title: "방법: 식 트리를 사용하여 동적 쿼리 빌드(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7de999848870de80996f308affde088088e32e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a>방법: 식 트리를 사용하여 동적 쿼리 빌드(C#)
LINQ에서는 식 트리를 사용하여 <xref:System.Linq.IQueryable%601>을 구현하는 데이터 소스를 대상으로 하는 구조적 쿼리를 나타냅니다. 예를 들어 LINQ 공급자는 관계형 데이터 저장소를 쿼리하기 위한 <xref:System.Linq.IQueryable%601> 인터페이스를 구현합니다. C# 컴파일러는 이러한 데이터 소스를 대상으로 하는 쿼리를 런타임에 식 트리를 작성하는 코드로 컴파일합니다. 그런 다음 쿼리 공급자는 식 트리 데이터 구조를 트래버스하고 데이터 소스에 적합한 쿼리 언어로 변환할 수 있습니다.  
  
 식 트리는 LINQ에서 <xref:System.Linq.Expressions.Expression%601> 형식의 변수에 할당된 람다 식을 나타내는 데에도 사용됩니다.  
  
 이 항목에서는 식 트리를 사용하여 동적 LINQ 쿼리를 만드는 방법을 설명합니다. 동적 쿼리는 컴파일 시 쿼리의 세부 정보를 알 수 없는 경우에 유용합니다. 예를 들어 최종 사용자가 하나 이상의 조건자를 지정하여 데이터를 필터링할 수 있는 사용자 인터페이스를 응용 프로그램에서 제공할 수 있습니다. LINQ를 쿼리에 사용하려면 이러한 종류의 응용 프로그램에서 식 트리를 사용하여 런타임에 LINQ 쿼리를 만들어야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 식 트리를 사용하여 `IQueryable` 데이터 소스에 대한 쿼리를 생성한 다음 실행하는 방법을 보여 줍니다. 코드에서 다음 쿼리를 나타내는 식 트리를 작성합니다.  
  
 `companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16)).OrderBy(company => company)`  
  
 <xref:System.Linq.Expressions> 네임스페이스의 팩터리 메서드는 전체 쿼리를 구성하는 식을 나타내는 식 트리를 만드는 데 사용됩니다. 표준 쿼리 연산자 메서드 호출을 나타내는 식은 이러한 메서드의 <xref:System.Linq.Queryable> 구현을 가리킵니다. 최종 식 트리는 `IQueryable` 데이터 소스 공급자의 <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> 구현에 전달되어 `IQueryable` 형식의 실행 가능한 쿼리를 만듭니다. 해당 쿼리 변수를 열거하여 결과를 가져옵니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 이 코드는 `Queryable.Where` 메서드에 전달되는 조건자에 고정 개수의 식을 사용합니다. 그러나 사용자 입력에 따라 달라지는 가변 개수의 조건자 식을 결합하는 응용 프로그램을 작성할 수 있습니다. 사용자 입력에 따라 쿼리에서 호출되는 표준 쿼리 연산자를 변경할 수도 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   **콘솔 응용 프로그램** 프로젝트를 새로 만듭니다.  
  
-   아직 참조되지 않은 경우 System.Core.dll에 대한 참조를 추가합니다.  
  
-   System.Linq.Expressions 네임스페이스를 포함합니다.  
  
-   예제의 코드를 복사하여 `Main` 메서드에 붙여넣습니다.  
  
## <a name="see-also"></a>참고 항목  
 [식 트리(C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)   
 [방법: 식 트리 실행(C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)   
 [방법: 런타임에 동적으로 조건자 필터 지정](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)