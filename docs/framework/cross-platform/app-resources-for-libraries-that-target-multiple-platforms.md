---
description: 'Obtenga más información sobre: Recursos de aplicación para bibliotecas destinadas a varias plataformas'
title: Recursos de aplicación para bibliotecas destinadas a varias plataformas
ms.date: 07/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multiple platforms, resources for
- resources [.NET Framework]
- .NET Framework, resources when targeting multiple platforms
- resources, for multiple platforms
- targeting multiple platforms, resources for
ms.assetid: 72c76f0b-7255-4576-9261-3587f949669c
ms.openlocfilehash: c6d1a8d19c58174e4b08842c4965dfbe3389d1e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402281"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Recursos de aplicación para bibliotecas destinadas a varias plataformas

Puede usar el tipo de proyecto de [biblioteca de clases portable](portable-class-library.md) de .NET Framework para garantizar que se pueda obtener acceso a los recursos de las bibliotecas de clases desde varias plataformas. Este tipo de proyecto está disponible en Visual Studio 2012 y tiene como destino el subconjunto portable de la biblioteca de clases .NET Framework. El uso de una biblioteca de clases portable garantiza que se pueda obtener acceso a la biblioteca desde aplicaciones de escritorio, aplicaciones de Silverlight, aplicaciones de Windows Phone y aplicaciones de la Tienda Windows 8.x.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 El proyecto de biblioteca de clases portable es solo un subconjunto muy limitado de los tipos del espacio de nombres <xref:System.Resources> disponible para la aplicación, pero podrá usar la clase <xref:System.Resources.ResourceManager> para recuperar recursos. Sin embargo, si está creando una aplicación mediante el uso de Visual Studio, debe usar el contenedor fuertemente tipado creado con Visual Studio en lugar de utilizar la clase <xref:System.Resources.ResourceManager> directamente.

 Para crear un contenedor fuertemente tipado en Visual Studio, establezca el **Modificador de acceso** del archivo de recursos principal como **Public** en el diseñador de recursos de Visual Studio. Esto crea un archivo [nombreArchivoRecursos].designer.cs o [nombreArchivoRecursos].designer.vb que incluye el contenedor ResourceManager fuertemente tipado. Para obtener más información sobre el uso de un contenedor de recursos fuertemente tipado, consulte la sección "Generación de una clase de recursos fuertemente tipados" en el tema [Resgen.exe (Generador de archivos de recursos)](../../framework/tools/resgen-exe-resource-file-generator.md).

## <a name="resource-manager-in-the-portable-class-library"></a>Administrador de recursos en la biblioteca de clases portable

 En un proyecto de biblioteca de clases portable, la clase <xref:System.Resources.ResourceManager> controla todo el acceso a los recursos. Dado que no se puede tener acceso a los tipos del espacio de nombres <xref:System.Resources>, como <xref:System.Resources.ResourceReader> y <xref:System.Resources.ResourceSet>, desde un proyecto de biblioteca de clases portable, estos no pueden utilizarse para obtener acceso a los recursos.

 El proyecto de biblioteca de clases portable incluye los cuatro miembros de <xref:System.Resources.ResourceManager> que se enumeran en la tabla siguiente. Estos constructores y métodos permiten crear una instancia de un objeto <xref:System.Resources.ResourceManager> y recuperar recursos de cadena.

|Miembro`ResourceManager`|Descripción|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Crea una instancia de <xref:System.Resources.ResourceManager> para obtener acceso al archivo de recursos con nombre que se encuentra en el ensamblado especificado.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Crea una instancia de <xref:System.Resources.ResourceManager> que corresponde al tipo especificado.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Recupera un recurso con nombre para la referencia cultural actual.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Recupera un recurso con nombre que pertenece a la referencia cultural especificada.|

 La exclusión de otros miembros de <xref:System.Resources.ResourceManager> de la biblioteca de clases portable significa que no pueden recuperarse objetos serializados, datos que no son de cadena e imágenes de un archivo de recursos. Para usar los recursos de una biblioteca de clases portable, debe almacenar todos los datos de objeto en formato de cadena. Por ejemplo, para almacenar valores numéricos en un archivo de recursos, estos pueden convertirse en cadenas. A continuación, podrán recuperarse y convertirse de nuevo en números con los métodos `Parse` o `TryParse` del tipo de datos numérico. Puede convertir imágenes u otros datos binarios en una representación de cadena mediante una llamada al método <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> y restaurarlos en una matriz de bytes mediante una llamada al método <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>La biblioteca de clases portable y las aplicaciones de la tienda Windows

 Los proyectos de biblioteca de clases portable almacenan recursos en archivos .resx que, a continuación, se compilan en archivos .resources y se incrustan en el ensamblado principal o en los ensamblados satélite en tiempo de compilación. Por otro lado, las aplicaciones de la Tienda Windows 8.x requieren que los recursos se almacenen en archivos .resw, que se compilan en un archivo de índice de recursos del paquete (PRI) único. Sin embargo, a pesar de los formatos de archivo incompatibles, la biblioteca de clases portable funcionará en una aplicación de la Tienda Windows 8.x.

 Para usar la biblioteca de clases desde una aplicación de la tienda Windows 8.x, agregue una referencia a esta en el proyecto de aplicación de la Tienda Windows. Visual Studio extraerá los recursos del ensamblado de forma transparente a un archivo .resw y lo usará para generar un archivo PRI desde el que Windows Runtime puede extraer recursos. En tiempo de ejecución, Windows Runtime ejecuta el código en la biblioteca de clases portable, pero recupera los recursos de la biblioteca de clases portable desde el archivo PRI.

 Si el proyecto de biblioteca de clases portable incluye recursos localizados, se usa el modelo de concentrador y radio para implementarlos como se haría con una biblioteca en una aplicación de escritorio. Para consumir el archivo de recursos principal y cualquier archivo de recursos localizado en la aplicación de la Tienda Windows 8.x, se agrega una referencia al ensamblado principal. En tiempo de compilación, Visual Studio extrae los recursos del archivo de recursos principal y de cualquier archivo de recursos localizado en archivos .resw independientes. A continuación, compila los archivos .resw en un único archivo PRI al que Windows Runtime obtiene acceso en tiempo de ejecución.

<a name="NonLoc"></a>

## <a name="example-non-localized-portable-class-library"></a>Ejemplo: biblioteca de clases portable no localizada

 En el siguiente ejemplo sencillo de biblioteca de clases portable no localizada, se usan recursos para almacenar los nombres de columnas y para determinar el número de caracteres que se van a reservar para los datos tabulares. En el ejemplo se usa un archivo denominado LibResources.resx para almacenar los recursos de cadena que se enumeran en la tabla siguiente.

|Nombre del recurso|Valor del recurso|
|-------------------|--------------------|
|Born|Fecha de nacimiento|
|BornLength|12|
|Hired|Fecha de contratación|
|HiredLength|12|
|ID|ID|
|ID.Length|12|
|Nombre|Nombre|
|NameLength|25|
|Título|Base de datos de empleados|

 El código siguiente define una clase `UILibrary` que usa el contenedor del Administrador de recursos denominado `resources` generado por Visual Studio cuando el **Modificador de acceso** del archivo cambia a **Public**. La clase UILibrary analiza los datos de cadena según sea necesario. . Tenga en cuenta que la clase está en el espacio de nombres `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de modo de consola. Requiere que se agregue una referencia a UILibrary.dll al proyecto de aplicación de consola.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de la Tienda Windows 8.x. Requiere que se agregue una referencia a UILibrary.dll al proyecto de aplicación de la Tienda Windows.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Ejemplo: biblioteca de clases portable localizada

 El siguiente ejemplo de biblioteca de clases portable localizada incluye recursos para las referencias culturales de francés (Francia) e inglés (Estados Unidos). La referencia cultural inglés (Estados Unidos) es la predeterminada de la aplicación; sus recursos se muestran en la tabla de la [sección anterior](app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). El archivo de recursos de la referencia cultural Francés (Francia) se denomina LibResources.fr-FR.resx y consta de los recursos de cadena que se enumeran en la tabla siguiente. El código fuente para la clase `UILibrary` es el mismo que se muestra en la sección anterior.

|Nombre del recurso|Valor del recurso|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|ID|ID|
|Nombre|Nom|
|Título|Base de données des employés|

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de modo de consola. Requiere que se agregue una referencia a UILibrary.dll al proyecto de aplicación de consola.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de la Tienda Windows 8.x. Requiere que se agregue una referencia a UILibrary.dll al proyecto de aplicación de la Tienda Windows. Usa la propiedad estática `ApplicationLanguages.PrimaryLanguageOverride` para establecer el idioma preferido de la aplicación en francés.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Resources.ResourceManager>
- [Recursos de aplicaciones de escritorio](../../framework/resources/index.md)
- [Empaquetar e implementar recursos](../../framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
