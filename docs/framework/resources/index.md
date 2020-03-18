---
title: Recursos en aplicaciones .NET
ms.date: 07/25/2018
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- deploying applications [.NET Core], resources
- application resources
- resource files
- satellite assemblies
- localization
- packaging application resources
- localizing resources
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
ms.openlocfilehash: f7db871c6643973ab18a5bb6bbfac7ab85a11a76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75346742"
---
# <a name="resources-in-net-apps"></a>Recursos en aplicaciones .NET

Casi todas las aplicaciones de calidad de producción tienen que utilizar recursos. Un recurso es cualquier dato no ejecutable que se implemente lógicamente con una aplicación. Los recursos pueden mostrarse en una aplicación como mensajes de error o como parte de la interfaz de usuario. Los recursos pueden contener datos con varios formatos, como objetos almacenados, cadenas e imágenes. (Para poder escribir objetos almacenados en un archivo de recursos, los objetos deben ser serializables). Si los datos se almacenan en un archivo de recursos, es posible modificarlos sin volver a compilar toda la aplicación. Esto también permite almacenar los datos en una sola ubicación y elimina la necesidad de confiar en los datos codificados de forma rígida almacenados en varias ubicaciones.

.NET Framework y .NET Core proporcionan numerosas prestaciones para crear y localizar recursos. Además, .NET admite un modelo simple para empaquetar e implementar recursos localizados.

Para obtener información sobre los recursos de ASP.NET, vea [Información general sobre los recursos de las páginas Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).

## <a name="create-and-localize-resources"></a>Creación y localización de recursos

En una aplicación no localizada, puede usar archivos de recursos como repositorio de los datos de la aplicación, especialmente para las cadenas que de otra manera podrían estar codificadas de forma rígida en varias ubicaciones del código fuente. Lo más común es que los recursos se creen como archivos de texto (.txt) o XML (.resx), y se use [Resgen.exe (Generador de archivo de recursos)](../tools/resgen-exe-resource-file-generator.md) para compilarlos en archivos binarios .resources. Estos archivos después se pueden incrustar en el archivo ejecutable de la aplicación mediante un compilador de lenguaje. Para más información sobre la creación de recursos, consulte [Crear archivos de recursos](creating-resource-files-for-desktop-apps.md).

También puede localizar los recursos de una aplicación para determinadas referencias culturales. Esto le permite compilar versiones localizadas (traducidas) de las aplicaciones. Cuando desarrolle una aplicación que utiliza recursos adaptados, debe designar una referencia cultural que sirva de referencia cultural neutra o de reserva cuyos recursos se utilizarán si no se dispone de recursos apropiados. Normalmente, los recursos de la referencia cultural neutra se almacenan en el ejecutable de la aplicación. Los recursos restantes para las distintas referencias culturales se almacenan en ensamblados satélite independientes. Para más información, consulte [Crear ensamblados satélite](creating-satellite-assemblies-for-desktop-apps.md).

## <a name="package-and-deploy-resources"></a>Empaquetar e implementar recursos

Los recursos adaptados de una aplicación se implementan en [ensamblados satélite](packaging-and-deploying-resources-in-desktop-apps.md). Un ensamblado satélite contiene los recursos de una única referencia cultural; no contiene código de la aplicación. En el modelo de implementación de ensamblados satélite, una aplicación se crea con un ensamblado predeterminado (que normalmente es el principal) y un ensamblado satélite para cada referencia cultural que admite la aplicación. Debido a que los ensamblados satélite no forman parte del ensamblado principal, los recursos correspondientes a una referencia cultural específica se pueden reemplazar o actualizar fácilmente sin reemplazar el ensamblado principal de la aplicación.

Es preciso determinar con sumo cuidado qué recursos formarán parte del ensamblado de recursos predeterminado de la aplicación. Como se trata de una parte del ensamblado principal, cualquier cambio que se realice en dicho ensamblado requerirá la reemplazo del ensamblado principal. Si no se proporciona ningún recurso predeterminado, se generará una excepción cuando el [proceso de reserva de recursos](packaging-and-deploying-resources-in-desktop-apps.md) intente buscarlo. En una aplicación diseñada correctamente, el uso de recursos jamás deberá producir una excepción.

Para más información, consulte el artículo [Empaquetar e implementar recursos](packaging-and-deploying-resources-in-desktop-apps.md).

## <a name="retrieve-resources"></a>Recuperar recursos

En tiempo de ejecución, la aplicación carga los recursos adaptados apropiados para cada subproceso, en función de la referencia cultural especificada por la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>. El valor de esta propiedad se deriva de la siguiente manera:

- Asignando directamente un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural adaptada a la propiedad <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>.

- Si no se ha asignado explícitamente una referencia cultural, recuperando la referencia cultural de la interfaz de usuario predeterminada del subproceso de la propiedad <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType>.

- Si no se ha asignado explícitamente ninguna referencia cultural a la interfaz de usuario predeterminada del subproceso, recuperando la referencia cultural del usuario actual del equipo local. Las implementaciones de .NET que se ejecutan en Windows realizan esta operación mediante una llamada a la función [`GetUserDefaultUILanguage`](/windows/desktop/api/winnls/nf-winnls-getuserdefaultuilanguage) de Windows.

Para obtener más información sobre cómo establecer la referencia cultural de la interfaz de usuario actual, vea las páginas de referencia de <xref:System.Globalization.CultureInfo> y de <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>.

Puede recuperar los recursos para la referencia cultural de la interfaz de usuario actual o para una referencia cultural concreta usando la clase <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Aunque la clase <xref:System.Resources.ResourceManager> se usa principalmente para recuperar recursos, el espacio de nombres <xref:System.Resources?displayProperty=nameWithType> contiene tipos adicionales que puede usar para recuperar recursos. Se incluyen los siguientes:

- La clase <xref:System.Resources.ResourceReader>, que permite enumerar recursos incrustados en un ensamblado o almacenados en un archivo binario .resources independiente. Resulta útil cuando no se conocen los nombres exactos de los recursos que están disponibles en tiempo de ejecución.

- La clase <xref:System.Resources.ResXResourceReader>, que permite recuperar recursos de un archivo XML (.resx).

- La clase <xref:System.Resources.ResourceSet>, que permite recuperar los recursos de una referencia cultural específica sin observar las reglas de reserva. Los recursos se pueden almacenar en un ensamblado o un archivo binario .resources independiente. También se puede desarrollar una implementación de <xref:System.Resources.IResourceReader> que permite usar la clase <xref:System.Resources.ResourceSet> para recuperar recursos de algún otro origen.

- La clase <xref:System.Resources.ResXResourceSet>, que permite cargar en la memoria todos los elementos de un archivo de recursos XML.

## <a name="see-also"></a>Vea también

- <xref:System.Globalization.CultureInfo>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>
- [Elementos esenciales de aplicaciones](../../standard/application-essentials.md)
- [Crear archivos de recursos](creating-resource-files-for-desktop-apps.md)
- [Empaquetar e implementar recursos](packaging-and-deploying-resources-in-desktop-apps.md)
- [Crear ensamblados satélite](creating-satellite-assemblies-for-desktop-apps.md)
- [Recuperar recursos](retrieving-resources-in-desktop-apps.md)
