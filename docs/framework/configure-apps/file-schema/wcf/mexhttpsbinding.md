---
title: '&lt;mexHttpsBinding&gt;'
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 759f28330bf54fb7be2f9f9ad67b4e45499b03bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltmexhttpsbindinggt"></a>&lt;mexHttpsBinding&gt;
HTTPS를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.  
  
 \<system.ServiceModel>  
\<바인딩 >  
\<mexHttpsBinding>  
  
## <a name="syntax"></a>구문  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`closeTimeout`|닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
|`name`|바인딩의 구성 이름을 포함하는 문자열입니다. 이 값은 바인딩의 ID로 사용되므로 고유해야 합니다. 각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다. 또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다. [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다. 기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.|  
|`openTimeout`|열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
|`receiveTimeout`|받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:10:00입니다.|  
|`sendTimeout`|보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다. 기본값은 00:01:00입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.|  
  
## <a name="remarks"></a>설명  
 이 바인딩은 기본적으로 인증서를 사용하여 전송 수준에서 보안을 지원할 수 있는 `WSHttpBinding` 바인딩입니다. 구성 및 메타 데이터 끝점을 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법:는 사용자 지정 Ws-metadata Exchange 바인딩 구성](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [하는 방법: 검색 메타 데이터를 통해가 아닌 MEX 바인딩을](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), 및 샘플 [메타 데이터 끝점을 보호 하는 사용자 지정](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [사용자 지정 바인딩을 통해 메타데이터 게시 및 검색](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [방법: MEX가 아닌 바인딩을 통해 메타데이터 검색](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [사용자 지정 보안 메타 데이터 끝점](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [메타데이터](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
