---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 35af7f5e10594617807384c20ab706ad675d11ef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755297"
---
# <a name="ltusemanagedpresentationgt"></a>&lt;useManagedPresentation&gt;
Elemento de enlace utilizado para comunicarse con un Servicio de token de seguridad de CardSpace que admite el perfil CardSpace de WS-Trust. Este elemento no tiene ningún atributo y está presente como modificador vacío.  
  
 \<system.serviceModel>  
\<enlaces >  
\<customBinding >  
\<enlace >  
\<useManagedPresentation >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enlace >](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 Un proveedor de identidad utiliza este elemento para expresar en su directiva el hecho de que admite el perfil CardSpace de WS-Trust. Los proveedores de identidad que publican este tipo de aserción de directiva deberían poder emitir tokens basados en ese perfil CardSpace.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
