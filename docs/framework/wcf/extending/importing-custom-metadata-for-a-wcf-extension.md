---
title: Importación de  metadatos personalizados para una extensión de WCF
ms.date: 03/30/2017
ms.assetid: 78beb28f-408a-4c75-9c3c-caefe9595b1a
ms.openlocfilehash: 99e2bd7c0ce1fd4a8154a0d6d9650487197d98d8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806866"
---
# <a name="importing-custom-metadata-for-a-wcf-extension"></a>Importación de  metadatos personalizados para una extensión de WCF
En Windows Communication Foundation (WCF), la importación de metadatos es el proceso de generar una representación abstracta de un servicio o los componentes de sus metadatos. Por ejemplo, puede importar WCF <xref:System.ServiceModel.Description.ServiceEndpoint> instancias, <xref:System.ServiceModel.Channels.Binding> instancias o <xref:System.ServiceModel.Description.ContractDescription> documentos de instancias de un archivo WSDL para un servicio. Para importar metadatos del servicio de WCF, utilice una implementación de la <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> clase abstracta. Tipos que derivan de la <xref:System.ServiceModel.Description.MetadataImporter> clase implementan la compatibilidad para la importación de formatos de metadatos que se benefician de WS-Policy importación lógica en WCF.  
  
 Los metadatos personalizados están compuestos de elementos XML que los importadores de metadatos proporcionados por el sistema no pueden importar. Normalmente, esto incluye extensiones WSDL personalizadas y aserciones de directivas personalizadas.  
  
 En esta sección se describe cómo importar extensiones WSDL personalizadas y aserciones de directivas. No se centra en el proceso de importación en sí. Para obtener más información sobre cómo usar los tipos que exportación e importación metadatos independientemente de si los metadatos están compatible por el sistema o personalizado, vea [exportar e importar metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Información general  
 El <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> tipo es la implementación de la <xref:System.ServiceModel.Description.MetadataImporter> incluido con WCF de clase abstracta. El tipo <xref:System.ServiceModel.Description.WsdlImporter> importa metadatos del WSDL con directivas adjuntas que se empaquetan en un objeto <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType>. Las aserciones de directivas y las extensiones WSDL que los importadores predeterminados no reconocen se pasan a cualquier directiva personalizada registrada e importadores del WSDL para su importación. Normalmente, los importadores se implementan para admitir los elementos de enlace definidos por el usuario o para modificar el contrato importado.  
  
 En esta sección se describe:  
  
1.  Cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>, que expone los datos de WSDL a los importadores personalizados antes de la generación de descripciones y la generación de código. Puede utilizar esta interfaz para examinar o modificar los tipos de descripción y codificar la compilación realizada utilizando un conjunto determinado de metadatos.  
  
2.  Cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>, que expone aserciones de directivas a importadores antes de la generación de objetos de descripción. Puede utilizar esta interfaz para examinar o modificar el enlace o el contrato basado en las directivas descargadas.  
  
 Para obtener más información acerca de la exportación de WSDL personalizada y aserciones de directivas, consulte [exportar metadatos personalizados para una extensión de WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="importing-custom-wsdl-extensions"></a>Importación de las extensiones WSDL personalizadas  
 Para agregar la compatibilidad para la importación de extensiones WSDL, implemente la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension> y, a continuación, agregue su implementación a la propiedad <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A>. <xref:System.ServiceModel.Description.WsdlImporter> también puede cargar las implementaciones de la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension> registradas en su archivo de configuración de la aplicación. Observe que se registran varios importadores de WSDL de forma predeterminada y el orden de los importadores de WSDL registrados es significativo.  
  
 Cuando <xref:System.ServiceModel.Description.WsdlImporter> carga y utiliza el importador de WSDL personalizado, primero se llama al método <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%2A> para habilitar la modificación de metadatos antes del proceso de importación. Después, se importan los contratos después de que el método <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%2A> se llame para habilitar la modificación de los contratos importados desde los metadatos. Finalmente, se llama al método <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%2A> para habilitar la modificación de extremos importados.  
  
 Para obtener más información, consulte [Cómo: importar personalizado WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md).  
  
### <a name="importing-custom-policy-assertions"></a>Importación de aserciones de directivas personalizadas  
 El <xref:System.ServiceModel.Description.WsdlImporter> tipo y la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) controlan automáticamente el procesamiento de una variedad de tipos de aserción de directiva en expresiones de directiva adjuntas a los documentos WSDL. Estas herramientas recogen, normalizan y fusionan mediante combinación expresiones de directivas adjuntas a los enlaces de WSDL y puertos WSDL.  
  
 Para agregar compatibilidad para la importación de aserciones de directivas personalizadas, implemente la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension> y, a continuación, agregue su implementación a la propiedad <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>. <xref:System.ServiceModel.Description.MetadataImporter> también puede cargar las implementaciones de la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension> registradas en su archivo de configuración de la aplicación. Observe que se registran varios importadores de directivas de forma predeterminada y el orden de los importadores de directivas registradas es significativo.  
  
 El sistema de metadatos llama repetidamente al método <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> en todas las extensiones de importación de directivas registradas para cada combinación de alternativas de directivas adjuntas al mensaje, operación y asuntos de directivas de extremos. Al importar un puerto WSDL, las directivas adjuntas al puerto y al enlace WSDL correspondiente se combinan antes de llamar en las extensiones de importación de directivas. Las alternativas de directivas se ponen a disposición a través de <xref:System.ServiceModel.Description.PolicyConversionContext> como objetos <xref:System.ServiceModel.Description.PolicyAssertionCollection>. Cada <xref:System.ServiceModel.Description.PolicyAssertionCollection> es una colección de aserciones de directivas representada por objetos <xref:System.Xml.XmlElement>.  
  
 Las propiedades <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A> y <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A> en el objeto <xref:System.ServiceModel.Description.PolicyConversionContext> exponen <xref:System.ServiceModel.Description.ContractDescription> y los objetos <xref:System.ServiceModel.Channels.BindingElement> que se importaron desde WSDL. Las extensiones de importación de directivas procesan aserciones de directivas encontrando instancias de un tipo de aserción de directiva determinado, realizando los cambios correspondientes en los objetos <xref:System.ServiceModel.Description.ContractDescription> o <xref:System.ServiceModel.Channels.BindingElement> y quitando, a continuación, las aserciones de directivas de la instancia <xref:System.ServiceModel.Description.PolicyAssertionCollection> correspondiente.  
  
 El atributo `wsp:Optional` y las expresiones de directivas anidadas no se normalizan, por lo que las extensiones de importación deben controlar estas construcciones de directivas. Asimismo, las extensiones de importación de directivas puede llamarse varias veces con los mismos objetos <xref:System.ServiceModel.Description.ContractDescription> y <xref:System.ServiceModel.Channels.BindingElement>, de modo que las extensiones de importación de directivas deberían ser robustas para este comportamiento.  
  
> [!IMPORTANT]
>  Los metadatos no válidos o inadecuados pueden pasarse al importador. Asegúrese de que los importadores personalizados son robustos para todos los formularios de XML.  
  
## <a name="see-also"></a>Vea también  
 [Importación de WSDL personalizado](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)  
 [Importación de aserciones de directivas personalizadas](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)  
 [Escritura de una extensión para ServiceContractGenerator](../../../../docs/framework/wcf/extending/how-to-write-an-extension-for-the-servicecontractgenerator.md)
