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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b32c2e354ea48e25ddb0aa561eb576cbfd89e3fb
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204738"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Recursos de aplicación para bibliotecas destinadas a varias plataformas
You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) project type to ensure that resources in your class libraries can be accessed from multiple platforms. This project type is available in Visual Studio 2012 and targets the portable subset of the .NET Framework class library. Using  a Portable Class Library ensures that your library can be accessed from desktop apps, Silverlight apps, Windows Phone apps, and Windows 8.x Store apps.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 The Portable Class Library project makes only a very limited subset of the types in the <xref:System.Resources> namespace available to your application, but it does allow you to use the <xref:System.Resources.ResourceManager> class to retrieve resources. Sin embargo, si está creando una aplicación mediante el uso de Visual Studio, debe usar el contenedor fuertemente tipado creado con Visual Studio en lugar de utilizar la clase <xref:System.Resources.ResourceManager> directamente.

 To create a strongly typed wrapper in Visual Studio, set the main resource file's **Access Modifier** in the Visual Studio Resource Designer to **Public**. Esto crea un archivo [nombreArchivoRecursos].designer.cs o [nombreArchivoRecursos].designer.vb que incluye el contenedor ResourceManager fuertemente tipado. For more information about using a strongly typed resource wrapper, see the "Generating a Strongly Typed Resource Class" section in the [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) topic.

## <a name="resource-manager-in-the-portable-class-library"></a>Resource Manager in the Portable Class Library
 In a Portable Class Library project, all access to resources is handled by the <xref:System.Resources.ResourceManager> class. Because types in the <xref:System.Resources> namespace, such as <xref:System.Resources.ResourceReader> and <xref:System.Resources.ResourceSet>, are not accessible from a Portable Class Library project, they cannot be used to access resources.

 The Portable Class Library project includes the four <xref:System.Resources.ResourceManager> members listed in the following table. Estos constructores y métodos permiten crear una instancia de un objeto <xref:System.Resources.ResourceManager> y recuperar recursos de cadena.

|Miembro`ResourceManager`|Descripción|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Crea una instancia de <xref:System.Resources.ResourceManager> para obtener acceso al archivo de recursos con nombre que se encuentra en el ensamblado especificado.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Crea una instancia de <xref:System.Resources.ResourceManager> que corresponde al tipo especificado.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Recupera un recurso con nombre para la referencia cultural actual.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Recupera un recurso con nombre que pertenece a la referencia cultural especificada.|

 The exclusion of other <xref:System.Resources.ResourceManager> members from the Portable Class Library means that serialized objects, non-string data, and images cannot be retrieved from a resource file. To use resources from a Portable Class Library, you should store all  object data in string form. Por ejemplo, para almacenar valores numéricos en un archivo de recursos, estos pueden convertirse en cadenas. A continuación, podrán recuperarse y convertirse de nuevo en números con los métodos `Parse` o `TryParse` del tipo de datos numérico. Puede convertir imágenes u otros datos binarios en una representación de cadena mediante una llamada al método <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> y restaurarlos en una matriz de bytes mediante una llamada al método <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>The Portable Class Library and Windows Store Apps
 Portable Class Library projects store resources in .resx files, which are then compiled into .resources files and embedded in the main assembly or in satellite assemblies at compile time. Windows 8.x Store apps, on the other hand, require resources to be stored in .resw files, which are then compiled into a single package resource index (PRI) file. However, despite the incompatible file formats, your Portable Class Library will work in a Windows 8.x Store app.

 To consume your class library from a Windows 8.x Store app, add a reference to it in your Windows Store app project. Visual Studio will transparently extract the resources from your assembly into a .resw file and use it to generate a PRI file from which the Windows Runtime can extract resources. At run time, the Windows Runtime executes the code in your Portable Class Library, but it retrieves your Portable Class Library's resources from the PRI file.

 If your Portable Class Library project includes localized resources, you use the hub-and-spoke model to deploy them just as you would for a library in a desktop app. To consume your main resource file and any localized resource files in your Windows 8.x Store app, you add a reference to the main assembly. En tiempo de compilación, Visual Studio extrae los recursos del archivo de recursos principal y de cualquier archivo de recursos localizado en archivos .resw independientes. It then compiles the .resw files into a single PRI file that the Windows Runtime accesses at run time.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Example: Non-Localized Portable Class Library
 The following simple, non-localized Portable Class Library example uses resources to store the names of columns and to determine the number of characters to reserve for tabular data. En el ejemplo se usa un archivo denominado LibResources.resx para almacenar los recursos de cadena que se enumeran en la tabla siguiente.

|Nombre del recurso|Valor del recurso|
|-------------------|--------------------|
|Born|Fecha de nacimiento|
|BornLength|12|
|Hired|Fecha de contratación|
|HiredLength|12|
|Id.|Id.|
|ID.Length|12|
|Name|Name|
|NameLength|25|
|Title|Base de datos de empleados|

 The following code defines a `UILibrary` class that uses the Resource Manager wrapper named `resources` generated by Visual Studio when the **Access Modifier** for the file is changed to **Public**. La clase UILibrary analiza los datos de cadena según sea necesario. . Tenga en cuenta que la clase está en el espacio de nombres `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de modo de consola. It requires a reference to UILibrary.dll to be added to the console app project.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 The following code illustrates how the `UILibrary` class and its resources can be accessed from a Windows 8.x Store app. It requires a reference to UILibrary.dll to be added to the Windows Store app project.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Example: Localized Portable Class Library
 The following localized Portable Class Library example includes resources for the French (France) and English (United States) cultures. The English (United States) culture is the app's default culture; its resources are shown in the table in the [previous section](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). El archivo de recursos de la referencia cultural Francés (Francia) se denomina LibResources.fr-FR.resx y consta de los recursos de cadena que se enumeran en la tabla siguiente. El código fuente para la clase `UILibrary` es el mismo que se muestra en la sección anterior.

|Nombre del recurso|Valor del recurso|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|Id.|Id.|
|Name|Nom|
|Title|Base de données des employés|

 El código siguiente muestra cómo obtener acceso a la clase `UILibrary` y a sus recursos desde una aplicación de modo de consola. It requires a reference to UILibrary.dll to be added to the console app project.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 The following code illustrates how the `UILibrary` class and its resources can be accessed from a Windows 8.x Store app. It requires a reference to UILibrary.dll to be added to the Windows Store app project. Usa la propiedad estática `ApplicationLanguages.PrimaryLanguageOverride` para establecer el idioma preferido de la aplicación en francés.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Resources.ResourceManager>
- [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)
- [Empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
