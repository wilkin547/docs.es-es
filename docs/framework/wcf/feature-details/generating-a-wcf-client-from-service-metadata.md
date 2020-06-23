---
title: Generación de un cliente WCF a partir de los metadatos de servicio
description: Descubra los distintos modificadores de Svcutil.exe utilizados para generar clientes WFC desde documentos de metadatos de servicio basados en WSDL o un archivo de directivas del servicio.
ms.date: 03/30/2017
ms.assetid: 27f8f545-cc44-412a-b104-617e0781b803
ms.openlocfilehash: f755a092fb3596349a6878c61fe414f4e0a9f9d1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247278"
---
# <a name="generating-a-wcf-client-from-service-metadata"></a>Generación de un cliente WCF a partir de los metadatos de servicio
En este tema se describe cómo utilizar los diversos modificadores de Svcutil.exe para generar los clientes a partir de documentos de metadatos.  
  
 Los documentos de metadatos pueden estar en un almacenamiento duradero o recuperarse en línea. La recuperación en línea sigue el protocolo WS-MetadataExchange o el protocolo Microsoft Discovery (DISCO). Svcutil.exe emite simultáneamente las siguientes solicitudes de metadatos para recuperar los metadatos:  
  
- Solicitud WS-MetadataExchange (MEX) a la dirección proporcionada.  
  
- Solicitud MEX a la dirección proporcionada con `/mex` anexado.  
  
- Solicitud de DISCO (mediante los <xref:System.Web.Services.Discovery.DiscoveryClientProtocol> servicios Web de ASP.net) a la dirección proporcionada.  
  
 Svcutil.exe genera el cliente basado en el lenguaje de descripción de servicios Web (WSDL) o en el archivo de directivas recibido desde el servicio. El nombre principal de usuario (UPN) se genera concatenando el nombre de usuario con " \@ " y agregando después un nombre de dominio completo (FQDN). Sin embargo, para los usuarios que se registraron en Active Directory, este formato no es válido y el UPN generado por la herramienta produce un error en la autenticación Kerberos con el siguiente mensaje de error: **error en el intento de inicio de sesión.** Para resolver este problema, debe corregir manualmente el archivo de cliente generado por la herramienta.  
  
```console
svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>  
```  
  
## <a name="referencing-and-sharing-types"></a>Hacer referencia a tipos y compartirlos  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/Reference\<file path>**|Tipos de referencia en el ensamblado especificado. Al generar clientes, utilice esta opción para especificar ensamblados que podrían contener tipos que representan los metadatos que se están importando.<br /><br /> Forma abreviada: `/r`|  
|**/excludeType:\<type>**|Especifica un nombre de tipo completo o calificado con el nombre de ensamblado que se va a excluir de los tipos de contrato a los que se hace referencia.<br /><br /> Forma abreviada: `/et`|  
  
## <a name="choosing-a-serializer"></a>Elección de un serializador  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/serializer:Auto**|Selecciona el serializador de forma automática. Esto utiliza el serializador `DataContract`. Si esto falla, se utiliza `XmlSerializer`.<br /><br /> Forma abreviada: `/ser:Auto`|  
|**/serializer:DataContractSerializer**|Genera tipos de datos que utilizan el serializador `DataContract` para la serialización y deserialización.<br /><br /> Forma abreviada: `/ser:DataContractSerializer`|  
|**/serializer:XmlSerializer**|Genera tipos de datos que usan el `XmlSerializer` para la serialización y deserialización.<br /><br /> Forma abreviada: `/ser:XmlSerializer`|  
|**/importXmlTypes**|Configura el serializador `DataContract` para que importe tipos que no sean de `DataContract` como tipos `IXmlSerializable`.<br /><br /> Forma abreviada: `/ixt`|  
|**/dataContractOnly**|Genera código para los tipos de `DataContract` únicamente. Se generan los tipos de `ServiceContract`.<br /><br /> Solo debería especificar archivos de metadatos locales para esta opción.<br /><br /> Forma abreviada: `/dconly`|  
  
## <a name="choosing-a-language-for-the-client"></a>Elección de un lenguaje para el cliente  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/Language\<language>**|Especifica el lenguaje de programación a utilizar para la generación de código. Proporcione un nombre de lenguaje registrado en el archivo Machine.config o el nombre completo de una clase que hereda de <xref:System.CodeDom.Compiler.CodeDomProvider>.<br /><br /> Valores: c#, cs, csharp, vb, vbs, visualbasic, vbscript, javascript, c++, mc, cpp<br /><br /> Valor predeterminado: csharp<br /><br /> Forma abreviada: `/l`<br /><br /> Para obtener más información, vea la clase <xref:System.CodeDom.Compiler.CodeDomProvider>.|  
  
## <a name="choosing-a-namespace-for-the-client"></a>Elección de un espacio de nombres para el cliente  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/Namespace\<string,string>**|Especifica una asignación desde un esquema WSDL o XML `targetNamespace` a un espacio de nombres de Common Language Runtime (CLR). El uso de un asterisco (*) para el `targetNamespace` asigna todos los `targetNamespaces` sin una asignación explícita a ese espacio de nombres de CLR.<br /><br /> Para asegurarse de que el nombre de contrato de mensaje no produce una colisión con el nombre de la operación, debería certificar o la referencia de tipo con dos puntos dobles (`::`) o asegurarse de que los nombres son únicos.<br /><br /> Valor predeterminado: Se deriva del espacio de nombres de destino del documento de esquema para `DataContracts`. El espacio de nombres predeterminado se utiliza para todos los otros tipos generados.<br /><br /> Forma abreviada: `/n`|  
  
## <a name="choosing-a-data-binding"></a>Elección de un enlace de datos  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/enableDataBinding**|Implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> en todos los tipos de `DataContract` para habilitar el enlace de datos.<br /><br /> Forma abreviada: `/edb`|  
  
## <a name="generating-configuration"></a>Generación de la configuración  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/config\<configFile>**|Especifica el nombre de archivo para el archivo de configuración generado.<br /><br /> Valor predeterminado: output.config|  
|**/mergeConfig**|Combina la configuración generada en un archivo existente en lugar de sobrescribir el archivo existente.|  
|**/noConfig**|No generar archivos de configuración.|  
  
## <a name="see-also"></a>Vea también

- [Utilización de los metadatos](using-metadata.md)
- [Información general de la arquitectura de metadatos](metadata-architecture-overview.md)
