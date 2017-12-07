---
title: "METAHOST_CONFIG_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_CONFIG_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_CONFIG_FLAGS
helpviewer_keywords: METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35b909f7b73657c8862c2d0645e5c5766df8beb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="55566-102">METAHOST_CONFIG_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="55566-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="55566-103">반환 된 가능한 플래그에 설명 된 `pdwConfigFlags` 의 매개 변수는 [iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드를 사용할 수 있음을 나타내는 및 설정는 `useLegacyV2RuntimeActivationPolicy` 특성에 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일의 합니다.</span><span class="sxs-lookup"><span data-stu-id="55566-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55566-104">구문</span><span class="sxs-lookup"><span data-stu-id="55566-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="55566-105">멤버</span><span class="sxs-lookup"><span data-stu-id="55566-105">Members</span></span>  
  
|<span data-ttu-id="55566-106">멤버</span><span class="sxs-lookup"><span data-stu-id="55566-106">Member</span></span>|<span data-ttu-id="55566-107">설명</span><span class="sxs-lookup"><span data-stu-id="55566-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="55566-108">`useLegacyV2RuntimeActivationPolicy` 특성에 있었던는 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55566-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="55566-109">`useLegacyV2RuntimeActivationPolicy` 특성은 존재 하 고 설정 하려면 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="55566-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="55566-110">`useLegacyV2RuntimeActivationPolicy` 특성은 존재 하 고 설정 하려면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="55566-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="55566-111">이 마스크에 반환 된 값에 적용 `pdwConfigFlags` 와 관련 된 값을 가져오려면 `useLegacyV2RuntimeActivationPolicy`합니다.</span><span class="sxs-lookup"><span data-stu-id="55566-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55566-112">설명</span><span class="sxs-lookup"><span data-stu-id="55566-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55566-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55566-113">Requirements</span></span>  
 <span data-ttu-id="55566-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55566-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55566-115">**헤더:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="55566-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="55566-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="55566-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55566-117">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55566-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55566-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55566-118">See Also</span></span>  
 [<span data-ttu-id="55566-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="55566-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="55566-120">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="55566-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)  
 [<span data-ttu-id="55566-121">\<시작 > 요소</span><span class="sxs-lookup"><span data-stu-id="55566-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)