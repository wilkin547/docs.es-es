---
title: Recursos de aplicaciones de escritorio | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- application resources
- resource files
- satellite assemblies
- localization
- packaging application resources
- localizing resources
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 3bbfaf3272444fbd2127f01ae4d5c9ca0db7bd39
ms.lasthandoff: 04/08/2017

---
# <a name="resources-in-desktop-apps"></a>Recursos de aplicaciones de escritorio
Casi todas las aplicaciones de calidad de producción tienen que utilizar recursos. Un recurso es cualquier dato no ejecutable que se implemente lógicamente con una aplicación. Los recursos pueden mostrarse en una aplicación como mensajes de error o como parte de la interfaz de usuario. Los recursos pueden contener datos con varios formatos, como objetos almacenados, cadenas e imágenes. (Para poder escribir objetos almacenados en un archivo de recursos, los objetos deben ser serializables). Si los datos se almacenan en un archivo de recursos, es posible modificarlos sin volver a compilar toda la aplicación. Esto también permite almacenar los datos en una sola ubicación y elimina la necesidad de confiar en los datos codificados de forma rígida almacenados en varias ubicaciones.  
  
 .NET Framework proporciona numerosas prestaciones para la creación y localización de recursos en las aplicaciones de escritorio. Además, .NET Framework admite un modelo simple para el empaquetado y la implementación de estos recursos localizados en las aplicaciones de escritorio.  
  
 Para información sobre los recursos de ASP.NET, consulte [Información general sobre recursos de páginas web ASP.NET](http://msdn.microsoft.com/library/0936b3b2-9e6e-4abe-9c06-364efef9dbbd) en el Centro para desarrolladores de Internet Explorer.  
  
 Las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] utilizan un modelo de recursos distinto del modelo de las aplicaciones de escritorio y almacenan los recursos en un único archivo de índice de recursos del paquete (PRI). Para información sobre los recursos en las aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], consulte [Crear y recuperar recursos en aplicaciones de la Tienda Windows](http://go.microsoft.com/fwlink/p/?LinkId=241674) en el Centro de desarrollo de Windows.  
  
## <a name="creating-and-localizing-resources"></a>Crear y localizar recursos  
 En una aplicación no localizada, puede usar archivos de recursos como repositorio de los datos de la aplicación, especialmente para las cadenas que de otra manera podrían estar codificadas de forma rígida en varias ubicaciones del código fuente. Lo más común es que los recursos se creen como archivos de texto (.txt) o XML (.resx), y se use [Resgen.exe (Generador de archivo de recursos)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) para compilarlos en archivos binarios .resources. Estos archivos después se pueden incrustar en el archivo ejecutable de la aplicación mediante un compilador de lenguaje. Para más información sobre la creación de recursos, consulte [Crear archivos de recursos](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md).  
  
 También puede localizar los recursos de una aplicación para determinadas referencias culturales. Esto le permite compilar versiones localizadas (traducidas) de las aplicaciones. Cuando desarrolle una aplicación que utiliza recursos adaptados, debe designar una referencia cultural que sirva de referencia cultural neutra o de reserva cuyos recursos se utilizarán si no se dispone de recursos apropiados. Normalmente, los recursos de la referencia cultural neutra se almacenan en el ejecutable de la aplicación. Los recursos restantes para las distintas referencias culturales se almacenan en ensamblados satélite independientes. Para más información, consulte [Crear ensamblados satélite](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md).  
  
## <a name="packaging-and-deploying-resources"></a>Empaquetar e implementar recursos  
 Los recursos adaptados de una aplicación se implementan en [ensamblados satélite](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md). Un ensamblado satélite contiene los recursos de una única referencia cultural; no contiene código de la aplicación. En el modelo de implementación de ensamblados satélite, una aplicación se crea con un ensamblado predeterminado (que normalmente es el principal) y un ensamblado satélite para cada referencia cultural que admite la aplicación. Debido a que los ensamblados satélite no forman parte del ensamblado principal, los recursos correspondientes a una referencia cultural específica se pueden reemplazar o actualizar fácilmente sin reemplazar el ensamblado principal de la aplicación.  
  
 Es preciso determinar con sumo cuidado qué recursos formarán parte del ensamblado de recursos predeterminado de la aplicación. Como se trata de una parte del ensamblado principal, cualquier cambio que se realice en dicho ensamblado requerirá la reemplazo del ensamblado principal. Si no se proporciona ningún recurso predeterminado, se generará una excepción cuando el [proceso de reserva de recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) intente buscarlo. En una aplicación diseñada correctamente, el uso de recursos jamás deberá producir una excepción.  
  
 Para más información, consulte el artículo [Empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  
  
## <a name="retrieving-resources"></a>Recuperar recursos  
 En tiempo de ejecución, la aplicación carga los recursos localizados apropiados para cada subproceso, en función de la referencia cultural especificada en la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>. El valor de esta propiedad se deriva de la siguiente manera:  
  
-   Asignando directamente un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural adaptada a la propiedad <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=fullName>.  
  
-   Si no se ha asignado explícitamente una referencia cultural, recuperando la referencia cultural predeterminada de la UI del subproceso de la propiedad <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=fullName>.  
  
-   Si no se ha asignado explícitamente una referencia cultural a la interfaz de usuario predeterminada del subproceso, recuperando la referencia cultural del usuario actual del equipo local llamando a la función `GetUserDefaultUILanguage` de Windows.  
  
 Para más información sobre cómo establecer la referencia cultural de la UI actual, consulte las páginas de referencia <xref:System.Globalization.CultureInfo> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>.  
  
 Puede recuperar los recursos para la referencia cultural de la UI actual o para una referencia cultural concreta con la clase <xref:System.Resources.ResourceManager?displayProperty=fullName>. Aunque la clase <xref:System.Resources.ResourceManager> se usa principalmente para recuperar recursos en las aplicaciones de escritorio, el espacio de nombres <xref:System.Resources?displayProperty=fullName> contiene tipos adicionales que puede usar para recuperar recursos. Se incluyen los siguientes:  
  
-   La clase <xref:System.Resources.ResourceReader>, que permite enumerar recursos incrustados en un ensamblado o almacenados en un archivo binario .resources independiente. Resulta útil cuando no se conocen los nombres exactos de los recursos que están disponibles en tiempo de ejecución.  
  
-   La clase <xref:System.Resources.ResXResourceReader>, que permite recuperar recursos de un archivo XML (.resx).  
  
-   La clase <xref:System.Resources.ResourceSet>, que permite recuperar los recursos de una referencia cultural específica sin observar las reglas de reserva. Los recursos se pueden almacenar en un ensamblado o un archivo binario .resources independiente. También se puede desarrollar una implementación de <xref:System.Resources.IResourceReader> que permite usar la clase <xref:System.Resources.ResourceSet> para recuperar recursos de algún otro origen.  
  
-   La clase <xref:System.Resources.ResXResourceSet>, que permite recuperar en la memoria todos los elementos de un archivo de recursos XML.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Globalization.CultureInfo>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 [Elementos esenciales de aplicaciones](../../../docs/standard/application-essentials.md)   
 [Crear archivos de recursos](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [Empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [Crear ensamblados satélite](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)   
 [Recuperar recursos](../../../docs/framework/resources/retrieving-resources-in-desktop-apps.md)
