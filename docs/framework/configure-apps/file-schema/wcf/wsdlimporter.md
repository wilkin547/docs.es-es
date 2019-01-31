---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: bd6c8661f94610d932ffee631aee7ad060f04c6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269320"
---
# <a name="wsdlimporter"></a>\<wsdlImporter>
Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.  
  
\<system.ServiceModel>  
\<client>  
\<metadata>  
\<wsdlImporters>  
\<wsdlImporter>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`type`|El tipo de este elemento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<wsdlImporters>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.|  
  
## <a name="remarks"></a>Comentarios  
 Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de punto de conexión. Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión. También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)
