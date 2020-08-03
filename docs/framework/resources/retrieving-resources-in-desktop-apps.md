---
title: Recuperar recursos de aplicaciones de escritorio
description: Recupere recursos de aplicaciones de escritorio. Empaquete recursos para la referencia cultural predeterminada (neutra) con el ensamblado principal y cree un ensamblado satélite para cada referencia cultural.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- resource files, packaging
- application resources, packaging
- localization
- versioning satellite assemblies
- retrieving localized resources
- application resources, deploying
- packaging application resources
- versioning resources
- translating resources into languages
- localizing resources
ms.assetid: eca16922-1c46-4f68-aefe-e7a12283641f
ms.openlocfilehash: db1156106690f8321b7fd5a2890c2aa44cfe17e3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166199"
---
# <a name="retrieving-resources-in-desktop-apps"></a>Recuperar recursos de aplicaciones de escritorio

Al trabajar con recursos localizados en aplicaciones de escritorio de .NET Framework, en principio se deberían empaquetar los recursos de la referencia cultural predeterminada o neutra con el ensamblado principal y, luego, crear un ensamblado satélite independiente para todos los idiomas o referencias culturales que admita la aplicación. Después podrá usar la clase <xref:System.Resources.ResourceManager> como se describe en la siguiente sección para obtener acceso a los recursos con nombre. Si opta por no insertar los recursos en el ensamblado principal y los ensamblados satélite, también puede obtener acceso directamente a los archivos .resources binarios, como se describe en la sección [Recuperar recursos desde archivos .resources](#from_file) , que aparece más adelante en este artículo.  Para recuperar recursos en las aplicaciones de la Tienda Windows 8.x, vea [Creación y recuperación de recursos en aplicaciones de la Tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/hh694557(v=vs.140)).  
  
<a name="from_assembly"></a>
## <a name="retrieving-resources-from-assemblies"></a>Recuperar recursos de ensamblados  
 La clase <xref:System.Resources.ResourceManager> proporciona acceso a los recursos en tiempo de ejecución. Puede usar el método <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> para recuperar recursos de cadena y el método <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType> o <xref:System.Resources.ResourceManager.GetStream%2A?displayProperty=nameWithType> para recuperar recursos que no son de cadena. Cada método tiene dos sobrecargas:  
  
- Una sobrecarga cuyo parámetro único es una cadena que contiene el nombre del recurso. El método intenta recuperar ese recurso para la referencia cultural del subproceso actual. Para obtener más información, consulte los métodos <xref:System.Resources.ResourceManager.GetString%28System.String%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%29>y <xref:System.Resources.ResourceManager.GetStream%28System.String%29> .  
  
- Una sobrecarga que tiene dos parámetros: una cadena que contiene el nombre del recurso y un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural cuyo recurso se debe recuperar. Si no se encuentra un recurso establecido para esa referencia cultural, el Administrador de recursos usa reglas de reserva para recuperar un recurso adecuado. Para obtener más información, consulte los métodos <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>y <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> .  
  
 El Administrador de recursos usa el proceso de reserva de recursos para controlar la forma en que la aplicación recupera los recursos específicos de referencia cultural. Para obtener más información, consulte la sección "El proceso de reserva de recursos" de [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md). Para obtener información sobre cómo crear una instancia de un objeto <xref:System.Resources.ResourceManager> , consulte la sección "Instantiating a ResourceManager Object" (Crear una instancia de un objeto ResourceManager) del tema de la clase <xref:System.Resources.ResourceManager> .  
  
### <a name="retrieving-string-data-an-example"></a>Recuperación de datos de cadena: Un ejemplo  
 En el ejemplo siguiente se llama al método <xref:System.Resources.ResourceManager.GetString%28System.String%29> para recuperar los recursos de cadena de la referencia cultural de interfaz de usuario actual. Incluye un recurso de cadena neutro para la referencia cultural de inglés (Estados Unidos) y recursos localizados para las referencias culturales de ruso (Rusia) y de francés (Francia). El siguiente recurso de inglés (Estados Unidos) está en un archivo denominado Strings.txt:  
  
```text
TimeHeader=The current time is  
```  
  
 El recurso de francés (Francia) está en un archivo denominado Strings.fr-FR.txt:  
  
```text
TimeHeader=L'heure actuelle est  
```  
  
 El recurso de ruso (Rusia) está en un archivo denominado Strings.ru-RU.txt:  
  
```text
TimeHeader=Текущее время —  
```  
  
 El código fuente de este ejemplo, que está en un archivo denominado GetString.cs para la versión de C# del código y GetString.vb para la versión de Visual Basic, define una matriz de cadenas que contiene el nombre de cuatro referencias culturales: las tres referencias culturales para las que los recursos están disponibles y la referencia cultural de español (España). Un bucle que se ejecuta cinco veces de forma aleatoria selecciona una de estas referencias culturales y la asigna a las propiedades <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> . Luego, llama al método <xref:System.Resources.ResourceManager.GetString%28System.String%29> para recuperar la cadena localizada, que aparecerá junto con la hora del día.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstring.cs#3)]
 [!code-vb[Conceptual.Resources.Retrieving#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstring.vb#3)]  
  
 El siguiente archivo por lotes (.bat) compila el ejemplo y genera los ensamblados satélite en los directorios correspondientes. Los comandos se proporcionan para el lenguaje C# y para el compilador. Si usa Visual Basic, cambie `csc` por `vbc`y `GetString.cs` por `GetString.vb`.  
  
```console
resgen strings.txt  
csc GetString.cs -resource:strings.resources  
  
resgen strings.fr-FR.txt  
md fr-FR  
al -embed:strings.fr-FR.resources -culture:fr-FR -out:fr-FR\GetString.resources.dll  
  
resgen strings.ru-RU.txt  
md ru-RU  
al -embed:strings.ru-RU.resources -culture:ru-RU -out:ru-RU\GetString.resources.dll  
```  
  
 Si la referencia cultural de interfaz de usuario actual es el español (España), tenga en cuenta que en el ejemplo se muestran los recursos del idioma inglés, ya que los recursos del idioma español no están disponibles y el inglés es la referencia cultural predeterminada del ejemplo.  
  
### <a name="retrieving-object-data-two-examples"></a>Recuperación de datos de objeto: dos ejemplos  
 Puede usar los métodos <xref:System.Resources.ResourceManager.GetObject%2A> y <xref:System.Resources.ResourceManager.GetStream%2A> para recuperar datos de objeto. Se incluyen los tipos de datos primitivos, los objetos serializables y los objetos que se almacenan en formato binario (como las imágenes).  
  
 En el ejemplo siguiente se usa el método <xref:System.Resources.ResourceManager.GetStream%28System.String%29> para recuperar un mapa de bits que se emplea en la ventana de inicio de una aplicación. El siguiente código fuente del archivo CreateResources.cs (para C#) o CreateResources.vb (para Visual Basic) genera un archivo .resx que contiene la imagen serializada. En este caso, la imagen se carga desde un archivo denominado SplashScreen.jpg; puede modificar el nombre del archivo para sustituir su propia imagen.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/createresources.cs#4)]
 [!code-vb[Conceptual.Resources.Retrieving#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/createresources.vb#4)]  
  
 El siguiente código recupera el recurso y muestra la imagen en un control <xref:System.Windows.Forms.PictureBox> .  
  
 [!code-csharp[Conceptual.Resources.Retrieving#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstream.cs#5)]
 [!code-vb[Conceptual.Resources.Retrieving#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstream.vb#5)]  
  
 Puede usar el siguiente archivo por lotes para compilar el ejemplo de C#. Si usa Visual Basic, cambie `csc` por `vbc`y la extensión del archivo de código fuente de `.cs` a `.vb`.  
  
```console
csc CreateResources.cs  
CreateResources  
  
resgen AppResources.resx  
  
csc GetStream.cs -resource:AppResources.resources  
```  
  
 En el siguiente ejemplo se usa el método <xref:System.Resources.ResourceManager.GetObject%28System.String%29?displayProperty=nameWithType> para deserializar un objeto personalizado. El ejemplo incluye un archivo de código fuente denominado UIElements.cs (UIElements.vb en el caso de Visual Basic) que define la siguiente estructura, denominada `PersonTable`. Esta estructura está pensada para usarse con una rutina de visualización general de tabla en la que se muestren los nombres localizados de las columnas de la tabla. Tenga en cuenta que la estructura `PersonTable` está marcada con el atributo <xref:System.SerializableAttribute> .  
  
 [!code-csharp[Conceptual.Resources.Retrieving#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example.cs#6)]
 [!code-vb[Conceptual.Resources.Retrieving#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#6)]  
  
 El siguiente código del archivo CreateResources.cs (CreateResources.vb para Visual Basic) crea un archivo de recursos XML denominado UIResources.resx que almacena un título de tabla y un objeto `PersonTable` que contiene información de una aplicación localizada para el idioma inglés.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example1.cs#7)]
 [!code-vb[Conceptual.Resources.Retrieving#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#7)]  
  
 Después, el siguiente código del archivo de código fuente GetObject.cs (GetObject.vb) recupera los recursos y los muestra en la consola.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example2.cs#8)]
 [!code-vb[Conceptual.Resources.Retrieving#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example2.vb#8)]  
  
 Puede crear el archivo de recursos y los ensamblados necesarios y ejecutar la aplicación con el siguiente archivo por lotes. Debe usar la opción `/r` para proporcionar a Resgen.exe una referencia a UIElements.dll para que pueda tener acceso a la información de la estructura `PersonTable` . Si usa C#, reemplace el nombre del compilador `vbc` por `csc`y la extensión `.vb` por `.cs`.  
  
```console
vbc -t:library UIElements.vb  
vbc CreateResources.vb -r:UIElements.dll  
CreateResources  
  
resgen UIResources.resx  -r:UIElements.dll  
vbc GetObject.vb -r:UIElements.dll -resource:UIResources.resources  
  
GetObject.exe  
```  
  
## <a name="versioning-support-for-satellite-assemblies"></a>Compatibilidad de versiones de los ensamblados satélite  
 De forma predeterminada, cuando el objeto <xref:System.Resources.ResourceManager> recupera los recursos solicitados, busca ensamblados satélite que tengan números de versión que coincidan con el número de versión del ensamblado principal. Después de implementar una aplicación, puede actualizar el ensamblado principal o los ensamblados satélite de recursos específicos. .NET Framework proporciona compatibilidad de las versiones del ensamblado principal y de los ensamblados satélite.  
  
 El atributo <xref:System.Resources.SatelliteContractVersionAttribute> proporciona compatibilidad de versiones para un ensamblado principal. Al especificar este atributo en el ensamblado principal de una aplicación, puede actualizar y volver a implementar un ensamblado principal sin tener que actualizar sus ensamblados satélite. Una vez actualizado el ensamblado principal, incremente el número de versión del ensamblado principal sin modificar el número de versión del contrato satélite. Cuando el Administrador de recursos recupere los recursos solicitados, cargará la versión del ensamblado satélite especificada por este atributo.  
  
 Los ensamblados de directiva de edición ofrecen compatibilidad de las versiones de los ensamblados satélite. Puede actualizar y volver a implementar un ensamblado satélite sin tener que actualizar el ensamblado principal. Después de actualizar un ensamblado satélite, incremente su número de versión y distribúyalo con un ensamblado de directiva de edición. En el ensamblado de directiva de edición, especifique que el nuevo ensamblado satélite es compatible con su versión anterior. El Administrador de recursos usará el atributo <xref:System.Resources.SatelliteContractVersionAttribute> para determinar la versión del ensamblado satélite, pero el cargador de ensamblados se enlazará con la versión del ensamblado satélite especificada por la directiva de edición. Para obtener más información sobre los ensamblados de directiva de edición, consulte [How to: Create a Publisher Policy](../configure-apps/how-to-create-a-publisher-policy.md)(Cómo crear una directiva de edición).  
  
 Para habilitar la compatibilidad completa de versiones de ensamblados, se recomienda implementar ensamblados con nombres seguros en la [caché global de ensamblados](../app-domains/gac.md) e implementar los ensamblados que no tengan nombres seguros en el directorio de la aplicación. Si quiere implementar ensamblados con nombres seguros en el directorio de la aplicación, no podrá aumentar el número de versión de un ensamblado satélite al actualizar el ensamblado. En lugar de ello, debe llevar a cabo una actualización local en la que deberá reemplazar el código existente por el código actualizado y conservar el mismo número de versión. Por ejemplo, si quiere actualizar la versión 1.0.0.0 de un ensamblado satélite con el nombre de ensamblado especificado por completo "MyApp.resources, Version=1.0.0.0, Culture=de, PublicKeyToken=b03f5f11d50a3a", sobrescríbalo con el archivo actualizado myApp.resources.dll que se ha compilado con el mismo nombre de ensamblado especificado por completo "myApp.resources, Version=1.0.0.0, Culture=de, PublicKeyToken=b03f5f11d50a3a". Tenga en cuenta que el uso de actualizaciones locales en los archivos del ensamblado satélite dificulta que una aplicación pueda determinar con exactitud la versión de un ensamblado satélite.  
  
 Para obtener más información sobre las versiones de los ensamblados, consulte [Assembly Versioning](../../standard/assembly/versioning.md) (Versiones de los ensamblados) y [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
<a name="from_file"></a>
## <a name="retrieving-resources-from-resources-files"></a>Recuperar recursos desde archivos .resources  
 Si decide no implementar recursos en los ensamblados satélite, puede usar un objeto <xref:System.Resources.ResourceManager> para obtener acceso directo a los recursos de los archivos .resources. Para ello, debe implementar correctamente los archivos .resources. Luego, deberá usar el método <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%2A?displayProperty=nameWithType> para crear una instancia de un objeto <xref:System.Resources.ResourceManager> y especificar el directorio que contiene los archivos .resources independientes.  
  
### <a name="deploying-resources-files"></a>Implementar archivos .resources  
 Al insertar archivos .resources en un ensamblado de aplicación y en ensamblados satélite, todos los ensamblados satélite tienen el mismo nombre de archivo, pero se encuentran en un subdirectorio que refleja la referencia cultural del ensamblado satélite. En cambio, al obtener acceso directo a los recursos desde los archivos .resources, puede colocar todos los archivos .resources en un solo directorio, que normalmente es un subdirectorio del directorio de la aplicación. El nombre del archivo .resources predeterminado de la aplicación consta solo de un nombre de raíz, sin ninguna indicación de la referencia cultural (por ejemplo, strings.resources). Los recursos de cada referencia cultural localizada se almacenan en un archivo cuyo nombre consta del nombre de raíz seguido de la referencia cultural (por ejemplo, strings.ja.resources o strings.de-DE.resources).

 En la siguiente ilustración se muestra dónde deben estar ubicados los archivos de recursos en la estructura de directorio. También proporciona las convenciones de nomenclatura de los archivos .resource.  

 ![Ilustración en la que se muestra el directorio principal de la aplicación.](./media/retrieving-resources-in-desktop-apps/resource-application-directory.gif)  
  
### <a name="using-the-resource-manager"></a>Usar el Administrador de recursos  
 Una vez creados los recursos y colocados en el directorio correspondiente, debe crear un objeto <xref:System.Resources.ResourceManager> para usar los recursos llamando al método <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%28System.String%2CSystem.String%2CSystem.Type%29> . El primer parámetro especifica el nombre de la raíz del archivo .resources predeterminado de la aplicación (en el ejemplo de la sección anterior sería "strings"). El segundo parámetro especifica la ubicación de los recursos (en el ejemplo anterior, "Resources"). El tercer parámetro especifica la implementación <xref:System.Resources.ResourceSet> que se va a usar. Si el tercer parámetro es `null`, se usará la clase <xref:System.Resources.ResourceSet> en tiempo de ejecución predeterminada.  
  
> [!NOTE]
> No implemente ninguna aplicación ASP.NET con archivos .resources independientes, ya que se pueden producir problemas de bloqueo y se puede interrumpir la implementación de XCOPY. Se recomienda implementar los recursos ASP.NET en ensamblados satélite. Para obtener más información, consulta [ASP.NET Web Page Resources Overview](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).  
  
 Después de crear una instancia del objeto <xref:System.Resources.ResourceManager> , debe usar los métodos <xref:System.Resources.ResourceManager.GetString%2A>, <xref:System.Resources.ResourceManager.GetObject%2A>y <xref:System.Resources.ResourceManager.GetStream%2A> como se ha descrito anteriormente para recuperar los recursos. A pesar de ello, la recuperación de recursos directamente desde los archivos .resources difiere de la recuperación de recursos insertados desde ensamblados. Al recuperar recursos desde archivos .resources, los métodos <xref:System.Resources.ResourceManager.GetString%28System.String%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%29>y <xref:System.Resources.ResourceManager.GetStream%28System.String%29> siempre recuperan los recursos de la referencia cultural predeterminada, independientemente de la referencia cultural actual. Para recuperar los recursos de la referencia cultural actual de la aplicación o de una referencia cultural en concreto, debe llamar al método <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>o <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> y especificar la referencia cultural cuyos recursos se van a recuperar. Para recuperar los recursos de la referencia cultural actual, especifique el valor de la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> como argumento `culture` . Si el Administrador de recursos no puede recuperar los recursos de `culture`, aplicará las reglas de reserva de recursos estándar para recuperar los recursos adecuados.  
  
### <a name="an-example"></a>Un ejemplo  
 En el ejemplo siguiente se muestra cómo el Administrador de recursos recupera los recursos directamente desde archivos .resources. El ejemplo consta de tres archivos de recursos basados en texto para las referencias culturales de inglés (Estados Unidos), francés (Francia) y ruso (Rusia). Inglés (Estados Unidos) es la referencia cultural predeterminada del ejemplo. Sus recursos están almacenados en el siguiente archivo, denominado Strings.txt:  
  
```text
Greeting=Hello  
Prompt=What is your name?  
```  
  
 Los recursos de la referencia cultural de francés (Francia) están almacenados en el siguiente archivo, que se denomina Strings.fr-FR.txt:  
  
```text
Greeting=Bon jour  
Prompt=Comment vous appelez-vous?  
```  
  
 Los recursos de la referencia cultural de ruso (Rusia) están almacenados en el siguiente archivo, que se denomina Strings.ru-RU.txt:  
  
```text
Greeting=Здравствуйте  
Prompt=Как вас зовут?  
```  
  
 A continuación se muestra el código fuente del ejemplo. En el ejemplo se crea una instancia de objetos <xref:System.Globalization.CultureInfo> para las referencias culturales de inglés (Estados Unidos), inglés (Canadá), francés (Francia) y ruso (Rusia); además, las convierte a todas en la referencia cultural actual. Luego, el método <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType> proporciona el valor de la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> como argumento `culture` para recuperar los recursos específicos de la referencia cultural adecuados.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example3.cs#9)]
 [!code-vb[Conceptual.Resources.Retrieving#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example3.vb#9)]  
  
 Puede compilar la versión de C# del ejemplo ejecutando el siguiente archivo por lotes. Si usa Visual Basic, reemplace `csc` por `vbc` y la extensión `.cs` por `.vb`.  
  
```console
Md Resources  
Resgen Strings.txt Resources\Strings.resources  
Resgen Strings.fr-FR.txt Resources\Strings.fr-FR.resources  
Resgen Strings.ru-RU.txt Resources\Strings.ru-RU.resources  
  
csc Example.cs  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Resources.ResourceManager>
- [Recursos de aplicaciones de escritorio](index.md)
- [Empaquetar e implementar recursos](packaging-and-deploying-resources-in-desktop-apps.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Crear y recuperar recursos en las aplicaciones de la Tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/hh694557(v=vs.140))
