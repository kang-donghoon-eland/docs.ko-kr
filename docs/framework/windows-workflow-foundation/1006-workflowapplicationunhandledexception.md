---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1006|  
|키워드|WFRuntime|  
|수준|오류|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 워크플로 응용 프로그램에서 처리되지 않은 예외가 발생했음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 WorkflowInstance Id: '%1'에 처리 되지 않은 예외가 발생 했습니다.  '%2', DisplayName 활동에서 발생 한 예외: '%3'.  다음과 같은 조치가 취해집니다: %4입니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|워크플로의 인스턴스 ID|  
|예외|`xs:string`|예외에 대한 예외 정보|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
