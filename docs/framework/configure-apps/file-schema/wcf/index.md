---
title: Esquema de configuración de WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: bcbc12d35dae59fcd43d5fbf2d4c936c8e4a4423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-configuration-schema"></a>Esquema de configuración de WCF
Elementos de configuración de Windows Communication Foundation (WCF) le permiten configurar las aplicaciones de cliente y servicio WCF. Puede usar la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) para crear y modificar los archivos de configuración para clientes y servicios. Puesto que los archivos de certificado tiene el formato como XML, debe familiarizarse con XML si desea modificarlos manualmente con un editor de texto. De lo contrario, puede encontrarse con problemas como no encontrar un atributo o una etiqueta de elemento XML. Esto se debe a que los atributos y las etiquetas del elemento XML distinguen entre mayúsculas y minúsculas.  
  
 El sistema de configuración de WCF se basa en el <xref:System.Configuration> espacio de nombres. Por consiguiente, puede usar todas las características estándar proporcionadas por el espacio de nombres <xref:System.Configuration>, como el bloqueo de configuración, el cifrado y la combinación para aumentar la seguridad de su aplicación y su configuración. Para obtener más información acerca del uso de estos conceptos, consulte los temas siguientes.  
  
 [Cifrar información de configuración](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [Bloquear opciones de configuración](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 En esta sección se describen todos los valores posibles de cada elemento de configuración y cómo interactúa con otros elementos de configuración de WCF. El siguiente mapa muestra el esquema de configuración de WCF.  
  
 ![Esquema de configuración de WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  También debería proteger las secciones de configuración de WCF en los archivos de configuración de aplicación (app.config) con acceso Control enumera (ACL) adecuada para evitar que las posibles amenazas de seguridad.  Por ejemplo, debería asegurarse de que sólo las personas adecuadas pueden tener acceso o modificar la configuración de seguridad en enlaces de la aplicación, o la sección modelo de servicio del archivo de configuración de un servicio.  
  
## <a name="in-this-section"></a>En esta sección  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 Describe el elemento `ServiceModel`.  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 Configura la herramienta SMSvcHost.exe.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 El elemento de nivel superior para establecer opciones al usar serializadores como <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Configurar aplicaciones de Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 Describe cómo configurar los clientes y servicios WCF.
