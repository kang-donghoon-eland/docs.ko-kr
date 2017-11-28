---
title: "COR_PUB_ENUMPROCESS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PUB_ENUMPROCESS
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_PUB_ENUMPROCESS
helpviewer_keywords: COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36f9e0650055c22d9a4e8c457a5ba01c295e4324
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="32ab6-102">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="32ab6-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="32ab6-103">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="32ab6-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32ab6-104">구문</span><span class="sxs-lookup"><span data-stu-id="32ab6-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="32ab6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="32ab6-105">Members</span></span>  
  
|<span data-ttu-id="32ab6-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="32ab6-106">Member name</span></span>|<span data-ttu-id="32ab6-107">설명</span><span class="sxs-lookup"><span data-stu-id="32ab6-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="32ab6-108">관리 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="32ab6-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32ab6-109">설명</span><span class="sxs-lookup"><span data-stu-id="32ab6-109">Remarks</span></span>  
 <span data-ttu-id="32ab6-110">관리 되지 않는 디버깅 API의 현재 버전 관리 프로세스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ab6-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32ab6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32ab6-111">Requirements</span></span>  
 <span data-ttu-id="32ab6-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32ab6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32ab6-113">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="32ab6-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="32ab6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32ab6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32ab6-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32ab6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ab6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32ab6-116">See Also</span></span>  
 [<span data-ttu-id="32ab6-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="32ab6-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)