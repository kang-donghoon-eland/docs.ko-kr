---
title: "INotifySource2::SetNotifyFilter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySource2.SetNotifyFilter
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c10b8ca9a49503b11e660a150e02ad59797664d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="59a6e-102">INotifySource2::SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="59a6e-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="59a6e-103">이 소스와 사용 하기 위해 알림 필터가 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="59a6e-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59a6e-104">구문</span><span class="sxs-lookup"><span data-stu-id="59a6e-104">Syntax</span></span>  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59a6e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59a6e-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="59a6e-106">[in] 비트 조합 된 [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) 디버거 API에 대 한 콜백을 식별 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59a6e-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="59a6e-107">[in] 에 대 한 포인터는 [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) 디버거 API에 대 한 스레드를 식별 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="59a6e-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59a6e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="59a6e-108">Return Value</span></span>  
 <span data-ttu-id="59a6e-109">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="59a6e-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59a6e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59a6e-110">Requirements</span></span>  
 <span data-ttu-id="59a6e-111">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="59a6e-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a6e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59a6e-112">See Also</span></span>  
 [<span data-ttu-id="59a6e-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59a6e-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="59a6e-114">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59a6e-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="59a6e-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59a6e-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)