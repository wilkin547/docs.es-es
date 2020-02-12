---
title: Recursos de aplicación para bibliotecas destinadas a varias plataformas
ms.date: 07/18/2018
ms.technology: dotnet-standard
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
ms.openlocfilehash: 3bf475117a85c2fced260dcc9460d55cd7007277
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123667"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Recursos de aplicación para bibliotecas destinadas a varias plataformas
Puede usar el tipo de proyecto .NET Framework [biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) para asegurarse de que se puede tener acceso a los recursos de las bibliotecas de clases desde varias plataformas. Este tipo de proyecto está disponible en Visual Studio 2012 y tiene como destino el subconjunto portable de la biblioteca de clases de .NET Framework. El uso de una biblioteca de clases portable garantiza que se puede tener acceso a la biblioteca desde aplicaciones de escritorio, aplicaciones de Silverlight, aplicaciones Windows Phone y aplicaciones de la tienda Windows 8. x.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 El proyecto de biblioteca de clases portable solo crea un subconjunto muy limitado de los tipos del espacio de nombres <xref:System.Resources> disponible para la aplicación, pero le permite usar la clase <xref:System.Resources.ResourceManager> para recuperar recursos. Sin embargo, si está creando una aplicación mediante el uso de Visual Studio, debe usar el contenedor fuertemente tipado creado con Visual Studio en lugar de utilizar la clase <xref:System.Resources.ResourceManager> directamente.

 Para crear un contenedor fuertemente tipado en Visual Studio, establezca el **modificador de acceso** del archivo de recursos principal en el diseñador de recursos de Visual Studio en **público**. Esto crea un archivo [nombreArchivoRecursos].designer.cs o [nombreArchivoRecursos].designer.vb que incluye el contenedor ResourceManager fuertemente tipado. Para obtener más información sobre el uso de un contenedor de recursos fuertemente tipado, vea la sección "generar una clase de recursos fuertemente tipados" en el tema [Resgen. exe (generador de archivos de recursos)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) .

## <a name="resource-manager-in-the-portable-class-library"></a>Administrador de recursos en la biblioteca de clases portable
 En un proyecto de biblioteca de clases portable, todo el acceso a los recursos se controla mediante la clase <xref:System.Resources.ResourceManager>. Dado que no se puede acceder a los tipos del espacio de nombres <xref:System.Resources>, como <xref:System.Resources.ResourceReader> y <xref:System.Resources.ResourceSet>, desde un proyecto de biblioteca de clases portable, no se pueden usar para tener acceso a los recursos.

 El proyecto de biblioteca de clases portable incluye los cuatro miembros <xref:System.Resources.ResourceManager> enumerados en la tabla siguiente. Estos constructores y métodos permiten crear una instancia de un objeto <xref:System.Resources.ResourceManager> y recuperar recursos de cadena.

|Miembro`ResourceManager`|Descripción|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Crea una instancia de <xref:System.Resources.ResourceManager> para obtener acceso al archivo de recursos con nombre que se encuentra en el ensamblado especificado.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Crea una instancia de <xref:System.Resources.ResourceManager> que corresponde al tipo especificado.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Recupera un recurso con nombre para la referencia cultural actual.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Recupera un recurso con nombre que pertenece a la referencia cultural especificada.|

 La exclusión de otros miembros de <xref:System.Resources.ResourceManager> de la biblioteca de clases portable significa que los objetos serializados, datos que no son de cadena e imágenes no se pueden recuperar de un archivo de recursos. Para usar recursos de una biblioteca de clases portable, debe almacenar todos los datos de objeto en formato de cadena. Por ejemplo, para almacenar valores numéricos en un archivo de recursos, estos pueden convertirse en cadenas. A continuación, podrán recuperarse y convertirse de nuevo en números con los métodos `Parse` o `TryParse` del tipo de datos numérico. Puede convertir imágenes u otros datos binarios en una representación de cadena mediante una llamada al método <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> y restaurarlos en una matriz de bytes mediante una llamada al método <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>La biblioteca de clases portable y las aplicaciones de la tienda Windows
 Los proyectos de biblioteca de clases portable almacenan los recursos en archivos. resx, que después se compilan en archivos. Resources y se incrustan en el ensamblado principal o en los ensamblados satélite en tiempo de compilación. Por otro lado, las aplicaciones de la tienda Windows 8. x requieren que los recursos se almacenen en archivos. resw, que se compilan en un solo archivo de índice de recursos de paquete (PRI). Sin embargo, a pesar de los formatos de archivo incompatibles, la biblioteca de clases portable funcionará en una aplicación de la tienda Windows 8. x.

 Para usar la biblioteca de clases desde una aplicación de la tienda Windows 8. x, agregue una referencia a ella en el proyecto de la aplicación de la tienda Windows. Visual Studio extrae de forma transparente los recursos del ensamblado en un archivo. resw y los usa para generar un archivo PRI a partir del cual el Windows Runtime puede extraer recursos. En tiempo de ejecución, el Windows Runtime ejecuta el código en la biblioteca de clases portable, pero recupera los recursos de la biblioteca de clases portable del archivo PRI.

 Si el proyecto de biblioteca de clases portable incluye recursos localizados, se usa el modelo de concentrador y radio para implementarlos de la misma forma que lo haría para una biblioteca en una aplicación de escritorio. Para consumir el archivo de recursos principal y los archivos de recursos localizados en la aplicación de la tienda Windows 8. x, agregue una referencia al ensamblado principal. En tiempo de compilación, Visual Studio extrae los recursos del archivo de recursos principal y de cualquier archivo de recursos localizado en archivos .resw independientes. A continuación, compila los archivos. resw en un único archivo PRI al que el Windows Runtime tiene acceso en tiempo de ejecución.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Ejemplo: biblioteca de clases portable no localizada
 En el siguiente ejemplo de biblioteca de clases portable simple y no localizada se usan recursos para almacenar los nombres de las columnas y para determinar el número de caracteres que se reservan para los datos tabulares. En el ejemplo se usa un archivo denominado LibResources.resx para almacenar los recursos de cadena que se enumeran en la tabla siguiente.

|Nombre del recurso|Valor del recurso|
|-------------------|--------------------|
|Born|Fecha de nacimiento|
|BornLength|12|
|Hired|Fecha de contratación|
|HiredLength|12|
|id|id|
|ID.Length|12|
|Nombre|Nombre|
|NameLength|25|
|Título|Base de datos de empleados|

 En el código siguiente se define una clase `UILibrary` que usa el contenedor de Administrador de recursos denominado `resources` generado por Visual Studio cuando el **modificador de acceso** del archivo se cambia a **Public**. La clase UILibrary analiza los datos de cadena según sea necesario. . Tenga en cuenta que la clase está en el espacio de nombres `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de modo de consola. Requiere que se agregue una referencia a UILibrary. dll al proyecto de aplicación de consola.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 En el código siguiente se muestra cómo se puede tener acceso a la clase de `UILibrary` y sus recursos desde una aplicación de la tienda Windows 8. x. Requiere que se agregue una referencia a UILibrary. dll al proyecto de aplicación de la tienda Windows.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Ejemplo: biblioteca de clases portable localizada
 En el siguiente ejemplo de biblioteca de clases portable traducida se incluyen los recursos para las referencias culturales de francés (Francia) e inglés (Estados Unidos). La referencia cultural de inglés (Estados Unidos) es la referencia cultural predeterminada de la aplicación. sus recursos se muestran en la tabla de la [sección anterior](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). El archivo de recursos de la referencia cultural Francés (Francia) se denomina LibResources.fr-FR.resx y consta de los recursos de cadena que se enumeran en la tabla siguiente. El código fuente para la clase `UILibrary` es el mismo que se muestra en la sección anterior.

|Nombre del recurso|Valor del recurso|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|id|id|
|Nombre|Nom|
|Título|Base de données des employés|

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de modo de consola. Requiere que se agregue una referencia a UILibrary. dll al proyecto de aplicación de consola.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 En el código siguiente se muestra cómo se puede tener acceso a la clase de `UILibrary` y sus recursos desde una aplicación de la tienda Windows 8. x. Requiere que se agregue una referencia a UILibrary. dll al proyecto de aplicación de la tienda Windows. Usa la propiedad estática `ApplicationLanguages.PrimaryLanguageOverride` para establecer el idioma preferido de la aplicación en francés.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Resources.ResourceManager>
- [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)
- [Empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
