---
title: Resgen.exe (Generador de archivos de recursos)
ms.date: 03/30/2017
helpviewer_keywords:
- resource files, .resources files
- resource files, .resx files
- resx files (resource files)
- .resources files
- files, converting
- Resource File Generator
- .resx files
- Resgen.exe
- resource files, converting
- converting files, Resource File Generator
- binary resources files
- embedding files in runtime binary executable
ms.assetid: 8ef159de-b660-4bec-9213-c3fbc4d1c6f4
ms.openlocfilehash: 5fc2bcb03ae6814d69e229ba083c1d5c44ae8ff3
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204625"
---
# <a name="resgenexe-resource-file-generator"></a>Resgen.exe (Generador de archivos de recursos)
El Generador de archivos de recursos (Resgen.exe) convierte archivos de texto (.txt o .restext) y archivos recursos basados en XML (.resx) en archivos binarios de Common Language Runtime (.resources) que se pueden incrustar en un archivo ejecutable binario o en un ensamblado satélite. (Vea [Creación de archivos de recursos](../resources/creating-resource-files-for-desktop-apps.md).)  
  
 Resgen.exe es una utilidad de conversión de recursos de uso general que realiza las tareas siguientes:  
  
- Convierte archivos .txt o .restext en archivos .resources o .resx. El formato de los archivos .restext es idéntico al formato de los archivos .txt. Sin embargo, la extensión .restext ayuda a identificar más fácilmente los archivos de texto que contienen definiciones de recursos.  
  
- Convierte archivos .resources en archivos de texto o archivos .resx.  
  
- Convierte archivos .resx en archivos de texto o archivos .resources.  
  
- Extrae los recursos de cadena de un ensamblado en un archivo .resw para poder usarlos en una aplicación de la Tienda Windows 8.x.  
  
- Crea una clase fuertemente tipada que proporciona acceso a cada uno de los recursos con nombre y a la instancia de <xref:System.Resources.ResourceManager>.  
  
 Si, por cualquier motivo, se produce un error en Resgen.exe, el valor devuelto será –1.  
  
 Para obtener ayuda sobre Resgen.exe, use el comando siguiente sin especificar ninguna opción; podrá ver las opciones y la sintaxis de los comandos de Resgen.exe:  
  
```console  
resgen  
```  
  
 También puede usar el modificador `/?`.  
  
```console  
resgen /?  
```  
  
 Si usa Resgen.exe para generar archivos .resources binarios, puede usar un compilador de lenguaje para incrustar los archivos binarios en ensamblados ejecutables, o puede usar la herramienta [Assembly Linker (Al.exe)](al-exe-assembly-linker.md) para compilarlos en ensamblados satélite.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
resgen  [-define:symbol1[,symbol2,...]] [/useSourcePath] filename.extension  | /compile filename.extension... [outputFilename.extension] [/r:assembly] [/str:lang[,namespace[,class[,file]]] [/publicclass]]   
```  
  
```console  
resgen filename.extension [outputDirectory]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro o modificador|DESCRIPCIÓN|  
|-------------------------|-----------------|  
|`/define:` *symbol1*[, *symbol2*,...]|A partir de .NET Framework 4.5, se admite la compilación condicional en archivos de recursos basados en texto (.txt o .restext). Si *symbol* corresponde a un símbolo incluido en el archivo de texto de entrada de una construcción `#ifdef`, el recurso de cadena asociado se incluye en el archivo .resources. Si el archivo de texto de entrada incluye una instrucción `#if !` con un símbolo que no se ha definido mediante el modificador `/define`, el recurso de cadena asociado se incluye en el archivo de recursos.<br /><br /> `/define` se omite si se usa con archivos de que no son de texto. Lo símbolos distinguen entre mayúsculas y minúsculas.<br /><br /> Para obtener más información sobre esta opción, vea [Compilar recursos de manera condicional](#Conditional) más adelante en este tema.|  
|`useSourcePath`|Especifica que el directorio actual del archivo de entrada se usará para resolver las rutas de acceso relativas.|  
|`/compile`|Permite especificar varios archivos .resx o de texto para convertirlos en varios archivos .resources en una única operación masiva. Si no especifica esta opción, solo podrá especificar un argumento de archivo de entrada. Los archivos de salida se denominan *filename*.resources.<br /><br /> Esta opción no se puede combinar con la opción `/str:`.<br /><br /> Para obtener más información sobre esta opción, vea [Compilar o convertir varios archivos](#Multiple) más adelante en este tema.|  
|`/r:` `assembly`|Hace referencia a los metadatos de los archivos de ensamblado especificados. Se usa al convertir los archivos .resx y permite que Resgen.exe serialice o deserialice los recursos de objeto. Se parece a las opciones `/reference:` o `/r:` de los compiladores de C# y Visual Basic.|  
|`filename.extension`|Especifica el nombre del archivo de entrada que se va a convertir. Si usa la primera de las dos sintaxis de línea de comandos (la más larga) que aparecen encima de esta tabla, el parámetro `extension` debe ser uno de los siguientes:<br /><br /> .txt o .restext<br /> Archivo de texto que se convertirá en un archivo .resources o en un archivo .resx. Los archivos de texto solo pueden contener recursos de cadena. Para obtener información sobre el formato de archivo, vea la sección sobre recursos en archivos de texto de [Creación de archivos de recursos](../resources/creating-resource-files-for-desktop-apps.md).<br /><br /> .resx<br /> Archivo de recursos basado en XML que se convertirá en un archivo .resources o en un archivo de texto (.txt o .restext).<br /><br /> .resources<br /> Archivo de recursos binario que se convertirá en un archivo .resx o en un archivo de texto (.txt o .restext).<br /><br /> Si usa la segunda de las dos sintaxis de línea de comandos (la más corta) que aparecen encima de esta tabla, el parámetro, `extension` debe ser el siguiente:<br /><br /> .exe o .dll<br /> Ensamblado de .NET Framework (archivo ejecutable o biblioteca) cuyos recursos de cadena se extraen en un archivo .resw para usarlos en el desarrollo de aplicaciones de la Tienda Windows 8.x.|  
|`outputFilename.extension`|Especifica el nombre y el tipo de archivo de recursos que se va a crear.<br /><br /> Este argumento es opcional cuando la conversión se realiza de un archivo .txt, .restext o .resx a un archivo .resources. Si no se especifica `outputFilename`, Resgen.exe anexa una extensión .resources al `filename` de entrada y escribe el archivo en el directorio que contiene `filename,extension`.<br /><br /> El argumento `outputFilename.extension` es obligatorio cuando se realiza la conversión de un archivo .resources. Cuando se convierte un archivo .resources en un archivo de recursos basado en XML, se debe especificar un nombre de archivo con la extensión .resx. Cuando se convierte un archivo .resources en un archivo de texto, se debe especificar un nombre de archivo con la extensión .txt o .restext. Solo se debe convertir un archivo .resources en un archivo .txt cuando el archivo .resources contiene únicamente valores de cadena.|  
|`outputDirectory`|Para las aplicaciones de la Tienda Windows 8.x, especifica el directorio en el que se escribirá un archivo .resw que contiene los recursos de cadena de `filename.extension`. `outputDirectory` ya debe existir.|  
|`/str:` `language[,namespace[,classname[,filename]]]`|Crea un archivo de clase de recursos fuertemente tipados en el lenguaje de programación especificado en la opción `language`. `language` puede constar de uno de los literales siguientes:<br /><br /> - Para C#: `c#`, `cs` o `csharp`.<br />- Para Visual Basic: `vb` o `visualbasic`.<br />- Para VBScript: `vbs` o `vbscript`.<br />- Para C++: `c++`, `mc` o `cpp`.<br />- Para JavaScript: `js`, `jscript` o `javascript`.<br /><br /> La opción `namespace` especifica el espacio de nombres predeterminado del proyecto, la opción `classname` especifica el nombre de la clase generada, y la opción `filename` especifica el nombre del archivo de clase.<br /><br /> La opción `/str:` solo permite un archivo de entrada, de modo que no se puede usar con la opción `/compile`.<br /><br /> Si se especifica `namespace`, pero no se especifica `classname`, el nombre de clase se deriva del nombre del archivo de salida (por ejemplo, los caracteres de subrayado se sustituyen por puntos). En consecuencia, es posible que los recursos fuertemente tipados no funcionen. Para evitarlo, especifique tanto el nombre de clase como el nombre del archivo de salida.<br /><br /> Para obtener más información sobre esta opción, vea [Generar una clase de recursos fuertemente tipados](#Strong) más adelante en este tema.|  
|`/publicClass`|Crea una clase de recursos fuertemente tipados como una clase pública. De forma predeterminada, la clase de recursos es `internal` en C# y `Friend` en Visual Basic.<br /><br /> Esta opción se omite si no se usa la opción `/str:`.|  
  
## <a name="resgenexe-and-resource-file-types"></a>Resgen.exe y los tipos de archivos de recursos  
 Para que Resgen.exe convierta correctamente los recursos, los archivos de texto y los archivos .resx deben tener el formato correcto.  
  
### <a name="text-txt-and-restext-files"></a>Archivos de texto (.txt y .restext)  
 Los archivos de texto (.txt o .restext) solo pueden contener recursos de cadena. Los recursos de cadena son útiles cuando se crea una aplicación que debe tener cadenas traducidas a varios idiomas. Por ejemplo, mediante el recurso de cadena apropiado, se pueden adaptar las cadenas de opciones de menú a la configuración regional de forma sencilla. Resgen.exe lee los archivos de texto que contienen pares nombre-valor, donde el nombre es una cadena que describe el recurso y el valor es la propia cadena de recursos.  
  
> [!NOTE]
> Para obtener información sobre el formato de los archivos .txt y .restext, vea la sección sobre recursos en archivos de texto de [Creación de archivos de recursos](../resources/creating-resource-files-for-desktop-apps.md).  
  
 Los archivos de texto que contienen recursos se deben guardar con codificación UTF-8 o Unicode (UTF-16), a menos que contengan únicamente caracteres latinos básicos (hasta U+007F). Resgen.exe quita los caracteres ANSI extendidos cuando procesa un archivo de texto guardado con codificación ANSI.  
  
 Resgen.exe comprueba si en el archivo de texto existen nombres de recursos duplicados. Si el archivo de texto contiene nombres de recursos duplicados, Resgen.exe emite una advertencia y omite el segundo valor.  
  
### <a name="resx-files"></a>Archivos .resx  
 El formato de archivo de recursos .resx consiste en entradas XML. En estas entradas XML puede especificar recursos de cadena, tal y como haría en los archivos de texto. Una ventaja importante de los archivos .resx sobre los archivos de texto es que también permiten especificar o incrustar objetos. Cuando se ve un archivo .resx, se puede observar la forma binaria de un objeto incrustado (por ejemplo, una imagen) cuando esta información binaria forma parte del manifiesto del recurso. Al igual que los archivos de texto, los archivos .resx se pueden abrir con un editor de texto (como el Bloc de notas o Microsoft Word) y escribir, analizar y manipular el contenido. Tenga en cuenta que esto requiere un conocimiento profundo de las etiquetas XML y de la estructura de archivos .resx. Para obtener más detalles sobre el formato de archivo .resx, vea la sección sobre recursos en archivos .resx de [Creación de archivos de recursos](../resources/creating-resource-files-for-desktop-apps.md).  
  
 Para crear un archivo .resources que contenga objetos incrustados que no son de cadena, debe usar Resgen.exe para convertir un archivo .resx que contenga objetos, o bien debe agregar los recursos de objeto al archivo directamente desde el código, utilizando los métodos que proporciona la clase <xref:System.Resources.ResourceWriter>.  
  
 Si el archivo .resx o .resources contiene objetos y usa Resgen.exe para convertirlo en un archivo de texto, todos los recursos de cadena se convertirán correctamente, pero los tipos de datos de los objetos que no son de cadena también se escribirán en el archivo como cadenas. Se perderán los objetos incrustados en la conversión y Resgen.exe notificará el error al recuperar los recursos.  
  
### <a name="converting-between-resources-file-types"></a>Convertir tipos de archivos de recursos  
 Al intentar convertir tipos de archivos de recursos en otros diferentes, es posible que Resgen.exe no pueda realizar la conversión o que pierda información sobre recursos específicos, en función de los tipos de archivos de origen y de destino. En la tabla siguiente se especifican los tipos de conversiones que se pueden realizar entre los distintos tipos de archivos de recursos.  
  
|Conversión de|A archivo de texto|A archivo .resx|A archivo .resw|A archivo .resources|  
|------------------|------------------|-------------------|-------------------|------------------------|  
|Archivo de texto (.txt o .restext)|--|Sin problemas|No compatibles|Sin problemas|  
|Archivo .resx|Se produce un error en la conversión si el archivo contiene recursos de no son de cadena (incluidos vínculos de archivo)|--|No compatibles|Sin problemas|  
|Archivo .resources|Se produce un error en la conversión si el archivo contiene recursos de no son de cadena (incluidos vínculos de archivo)|Sin problemas|No compatibles|--|  
|Ensamblado .exe o .dll|No compatibles|No compatibles|Solo los recursos de cadena (incluidos los nombres de ruta de acceso) se reconocen como recursos|No compatibles|  
  
## <a name="performing-specific-resgenexe-tasks"></a>Realizar tareas específicas de Resgen.exe  
 Puede usar la herramienta Resgen.exe de varias maneras: para compilar un archivo de recursos basado en texto o en XML en un archivo binario, para realizar conversiones entre los distintos formatos de archivo de recursos, y para generar una clase que incluya la funcionalidad <xref:System.Resources.ResourceManager> y proporcione acceso a los recursos. En esta sección se proporciona información detallada sobre cada tarea.  
  
- [Compilar recursos en un archivo binario](resgen-exe-resource-file-generator.md#Compiling)  
  
- [Convertir tipos de archivos de recursos](resgen-exe-resource-file-generator.md#Convert)  
  
- [Compilar o convertir varios archivos](resgen-exe-resource-file-generator.md#Multiple)  
  
- [Exportar recursos a un archivo .resw](resgen-exe-resource-file-generator.md#Exporting)  
  
- [Compilar recursos de manera condicional](resgen-exe-resource-file-generator.md#Conditional)  
  
- [Generar una clase de recursos fuertemente tipados](resgen-exe-resource-file-generator.md#Strong)  
  
<a name="Compiling"></a>   
### <a name="compiling-resources-into-a-binary-file"></a>Compilar recursos en un archivo binario  
 El uso más común de Resgen.exe es compilar un archivo de recursos basado en texto (un archivo .txt o .restext) o un archivo de recursos basado en XML (un archivo .resx) en un archivo .resources binario. El archivo de salida se puede insertar en un ensamblado principal mediante un compilador de lenguaje, o en un ensamblado satélite mediante [Assembly Linker (AL.exe)](al-exe-assembly-linker.md).  
  
 La sintaxis para compilar un archivo de recursos es la siguiente:  
  
```console  
resgen inputFilename [outputFilename]   
```  
  
 donde los parámetros son:  
  
 `inputFilename`  
 El nombre de archivo, incluida la extensión, del archivo de recursos que se va a compilar. Resgen.exe compila únicamente archivos con la extensión .txt, .restext o .resx.  
  
 `outputFilename`  
 Nombre del archivo de salida. Si omite `outputFilename`, Resgen.exe crea un archivo .resources con el mismo nombre de archivo raíz que `inputFilename` y lo sitúa en el directorio en el que se encuentra `inputFilename`. Si `outputFilename` incluye una ruta de acceso a un directorio, dicho directorio debe existir.  
  
 Proporcione un espacio de nombres completo para el archivo .resources. Inclúyalo en el nombre de archivo y sepárelo del nombre de archivo raíz mediante un punto. Por ejemplo, si `outputFilename` es `MyCompany.Libraries.Strings.resources`, el espacio de nombres es MyCompany.Libraries.  
  
 El comando siguiente lee los pares nombre-valor de Resources.txt y escribe un archivo .resources binario denominado Resources.resources. Dado que el nombre del archivo de salida no se especifica de forma explícita, de forma predeterminada recibe el mismo nombre que el archivo de entrada.  
  
```console  
resgen Resources.txt   
```  
  
 El comando siguiente lee los pares nombre-valor de Resources.restext y escribe un archivo de recursos binario denominado StringResources.resources.  
  
```console  
resgen Resources.restext StringResources.resources  
```  
  
 El comando siguiente lee un archivo de entrada basado en XML denominado Resources.resx y escribe un archivo .resources binario denominado Resources.resources.  
  
```console  
resgen Resources.resx Resources.resources  
```  
  
<a name="Convert"></a>   
### <a name="converting-between-resource-file-types"></a>Convertir tipos de archivos de recursos  
 Además de compilar archivos de recursos basados en texto o en XML en archivos .resources binarios, Resgen.exe puede convertir cualquier tipo de archivo compatible en cualquier otro tipo de archivo compatible. Esto significa que puede realizar las conversiones siguientes:  
  
- Archivos .txt y .restext en archivos .resx.  
  
- Archivos .resx en archivos .txt y .restext.  
  
- Archivos .resources en archivos .txt y .restext.  
  
- Archivos .resources en archivos .resx.  
  
 La sintaxis es la misma que la mostrada en la sección anterior.  
  
 Además, puede usar Resgen.exe para convertir recursos incrustados de un ensamblado de .NET Framework en un archivo .resw para poder usarlo en aplicaciones de la Tienda Windows 8.x.  
  
 El comando siguiente lee un archivo de recursos binario denominado Resources.resources y escribe un archivo de entrada basado en XML denominado Resources.resx.  
  
```console  
resgen Resources.resources Resources.resx  
```  
  
 El comando siguiente lee un archivo de recursos basado en texto denominado StringResources.txt y escribe un archivo de recursos basado en XML denominado LibraryResources.resx. Además de contener recursos de cadena, el archivo .resx también se puede usar para almacenar recursos que no son de cadena.  
  
```console  
resgen StringResources.txt LibraryResources.resx  
```  
  
 Los dos comandos siguientes leen un archivo de recursos basado en XML denominado Resources.resx y escriben archivos de texto denominados Resources.txt y Resources.restext. Tenga en cuenta que si el archivo .resx contiene objetos incrustados, no se convertirán de forma precisa en los archivos de texto.  
  
```console  
resgen Resources.resx Resources.txt  
resgen Resources.resx Resources.restext  
```  
  
<a name="Multiple"></a>   
### <a name="compiling-or-converting-multiple-files"></a>Compilar o convertir varios archivos  
 Puede usar el modificador `/compile` para convertir el formato de una lista de archivos de recursos en otro formato en una única operación. La sintaxis es la siguiente:  
  
```console  
resgen /compile filename.extension [filename.extension...]  
```  
  
 El comando siguiente compila tres archivos, StringResources.txt, TableResources.resw e ImageResources.resw, en archivos .resources independientes denominados StringResources.resources, TableResources.resources e ImageResources.resources.  
  
```console  
resgen /compile StringResources.txt TableResources.resx ImageResources.resx  
```  
  
<a name="Exporting"></a>   
### <a name="exporting-resources-to-a-resw-file"></a>Exportar recursos a un archivo .resw  
 Si va a desarrollar una aplicación de la Tienda Windows 8.x, quizás desee usar recursos de una aplicación de escritorio existente. Sin embargo, los dos tipos de aplicaciones admiten formatos de archivo diferentes. En las aplicaciones de escritorio, los recursos de los archivos de texto (.txt o .restext) o de los archivos .resx se compilan en archivos .resources binarios. En las aplicaciones de la Tienda Windows 8.x, los archivos .resw se compilan en archivos de índice de recursos del paquete (PRI) binarios. Puede usar la herramienta Resgen.exe cubrir esta carencia extrayendo los recursos de un archivo ejecutable o un ensamblado satélite y escribiéndolos en uno o varios archivos .resw que se podrán usar para desarrollar una aplicación de la Tienda Windows 8.x.  
  
> [!IMPORTANT]
> Visual Studio controla automáticamente todas las conversiones necesarias para incorporar los recursos de una biblioteca portable en una aplicación de la Tienda Windows 8.x. El uso de Resgen.exe para convertir directamente los recursos de un ensamblado al formato de archivo .resw solo es de interés para los desarrolladores que desean desarrollar una aplicación de la Tienda Windows 8.x fuera de Visual Studio.  
  
 La sintaxis para generar archivos .resw a partir de un ensamblado es la siguiente:  
  
```console  
resgen filename.extension  [outputDirectory]  
```  
  
 donde los parámetros son:  
  
 `filename.extension`  
 El nombre de un ensamblado de .NET Framework (un archivo ejecutable o un archivo .DLL). Si el archivo no contiene ningún recurso, Resgen.exe no crea ningún archivo.  
  
 `outputDirectory`  
 El directorio existente en el que se escribirán los archivos .resw. Si se omite `outputDirectory`, los archivos .resw se escriben en el directorio actual. Resgen.exe crea un archivo .resw para cada archivo .resources del ensamblado. El nombre de archivo raíz del archivo .resw es el mismo que el nombre raíz del archivo .resources.  
  
 El siguiente comando crea un archivo .resw en el directorio Win8Resources para cada archivo .resources incrustado en MyApp.exe:  
  
```console  
resgen MyApp.exe Win8Resources  
```  
  
<a name="Conditional"></a>   
### <a name="conditionally-compiling-resources"></a>Compilar recursos de manera condicional  
 A partir de .NET Framework 4.5, Resgen.exe admite la compilación condicional de recursos de cadena en archivos de texto (.txt y .restext). Esto permite usar un único archivo de recursos basado en texto en varias configuraciones de compilación.  
  
 En un archivo .txt o .restext, use la construcción `#ifdef`…`#endif` para incluir un recurso en el archivo .resources binario si se ha definido un símbolo, y use la construcción `#if !`... `#endif` para incluir un recurso si no se ha definido ningún símbolo. En tiempo de compilación, los símbolos se definen mediante la opción `/define:` seguida de una lista de símbolos delimitados por comas. La comparación distingue entre mayúsculas y minúsculas. El formato de mayúsculas y minúsculas definido en `/define` debe coincidir con el de los archivos de texto que se van a compilar.  
  
 Por ejemplo, el siguiente archivo denominado UIResources.rext incluye un recurso de cadena denominado `AppTitle` que puede tomar uno de tres valores posibles dependiendo de si se han definido los símbolos denominados `PRODUCTION`, `CONSULT` o `RETAIL`.  
  
```text
#ifdef PRODUCTION  
AppTitle=My Software Company Project Manager   
#endif  
#ifdef CONSULT  
AppTitle=My Consulting Company Project Manager  
#endif  
#ifdef RETAIL  
AppTitle=My Retail Store Project Manager  
#endif  
FileMenuName=File  
```  
  
 A continuación, el archivo se puede compilar en un archivo .resources binario con el comando siguiente:  
  
```console  
resgen /define:CONSULT UIResources.restext  
```  
  
 Esto genera un archivo .resources que contiene dos recursos de cadena. El valor del recurso `AppTitle` es "My Consulting Company Project Manager".  
  
<a name="Strong"></a>   
### <a name="generating-a-strongly-typed-resource-class"></a>Generar una clase de recursos fuertemente tipados  
 Resgen.exe admite recursos fuertemente tipados y encapsula el acceso a los recursos mediante la creación de clases que contienen un conjunto de propiedades estáticas de solo lectura. A la hora de recuperar recursos, esto proporciona una alternativa a la llamada a los métodos de la clase <xref:System.Resources.ResourceManager> directamente. Para habilitar la compatibilidad con los recursos fuertemente tipados en Resgen.exe, use la opción `/str`, que incluye la funcionalidad de la clase <xref:System.Resources.Tools.StronglyTypedResourceBuilder>. Cuando se especifica la opción `/str`, el resultado de Resgen.exe es una clase que contiene propiedades fuertemente tipadas que coinciden con los recursos a los que se hace referencia en el parámetro de entrada. Esta clase proporciona acceso de solo lectura fuertemente tipado a los recursos que están disponibles en el archivo procesado.  
  
 La sintaxis para crear un recurso fuertemente tipado es la siguiente:  
  
```console  
resgen inputFilename [outputFilename] /str:language[,namespace,[classname[,filename]]] [/publicClass]  
```  
  
 Los parámetros y los modificadores son los siguientes:  
  
 `inputFilename`  
 El nombre de archivo, incluida la extensión, del archivo de recursos para el que se generará una clase de recursos fuertemente tipados. El archivo puede ser un archivo basado en texto o en XML, o un archivo .resources binario, y puede tener la extensión .txt, .restext, .resw o .resources.  
  
 `outputFilename`  
 Nombre del archivo de salida. Si `outputFilename` incluye una ruta de acceso a un directorio, dicho directorio debe existir. Si omite `outputFilename`, Resgen.exe crea un archivo .resources con el mismo nombre de archivo raíz que `inputFilename` y lo sitúa en el directorio en el que se encuentra `inputFilename`.  
  
 `outputFilename` puede ser un archivo basado en texto, un archivo basado en XML o un archivo .resources. binario. Si la extensión de archivo de `outputFilename` es distinta de la extensión de archivo de `inputFilename`, Resgen.exe realiza la conversión del archivo.  
  
 Si `inputFilename` es un archivo .resources, Resgen.exe lo copia si `outputFilename` también es un archivo .resources. Si se omite `outputFilename`, Resgen.exe sobrescribe `inputFilename` con un archivo .resources idéntico.  
  
 *language*  
 El lenguaje en el que se genera el código fuente para la clase de recursos fuertemente tipados. Los valores posibles son `cs`, `C#` y `csharp` para código de C#, `vb` y `visualbasic` para código de Visual Basic, `vbs` y `vbscript` para código VBScript, y `c++`, `mc` y `cpp` para código de C++.  
  
 *namespace*  
 El espacio de nombres que contiene la clase de recursos fuertemente tipados. El archivo .resources y la clase de recursos deben tener el mismo espacio de nombres. Para obtener información sobre la especificación del espacio de nombres en `outputFilename`, vea [Compilar recursos en un archivo binario](resgen-exe-resource-file-generator.md#Compiling). Si se omite *namespace*, la clase de recursos no está contenida en un espacio de nombres.  
  
 *classname*  
 El nombre de la clase de recursos fuertemente tipados. Este se debe corresponder con el nombre raíz del archivo .resources. Por ejemplo, si Resgen.exe genera un archivo .resources denominado MyCompany.Libraries.Strings.resources, el nombre de la clase de recursos fuertemente tipados es Strings. Si se omite *classname*, la clase generada se deriva del nombre raíz de `outputFilename`. Si se omite `outputFilename`, la clase generada se deriva del nombre raíz de `inputFilename`.  
  
 *classname* no puede contener caracteres no válidos, como espacios insertados. Si *classname* contiene espacios insertados, o si *classname* se genera de forma predeterminada a partir de *inputFilename*, e *inputFilename* contiene espacios insertados, Resgen.exe reemplaza todos los caracteres no válidos por un carácter de subrayado (\_).  
  
 *filename*  
 Nombre del archivo de clase.  
  
 `/publicclass`  
 Convierte la clase de recursos fuertemente tipados en una clase pública en lugar de `internal` (en C#) o `Friend` (en Visual Basic). Esto permite tener acceso a los recursos desde fuera del ensamblado en el que están incrustados.  
  
> [!IMPORTANT]
> Cuando se crea una clase de recursos fuertemente tipados, el nombre del archivo .resources debe coincidir con el espacio de nombres y el nombre de clase del código generado. Sin embargo, Resgen.exe permite especificar opciones que generan un archivo .resources con un nombre incompatible. Para evitar este comportamiento, cambie el nombre del archivo de salida tras su generación.  
  
 La clase de recursos fuertemente tipados se compone de los elementos siguientes:  
  
- Un constructor sin parámetros, que se puede usar para crear instancias de la clase de recursos fuertemente tipados.  
  
- Una propiedad `static` (C#) o `Shared` (Visual Basic) de solo lectura de `ResourceManager`, que devuelve la instancia de <xref:System.Resources.ResourceManager> que administra el recurso fuertemente tipado.  
  
- Una propiedad estática `Culture`, que permite establecer la referencia cultural usada para la recuperación de los recursos. De manera predeterminada, su valor es `null`, lo que significa que se usa la referencia cultural de la interfaz de usuario actual.  
  
- Una propiedad `static` (C#) o `Shared` (Visual Basic) de solo lectura para cada recurso del archivo .resources. El nombre de la propiedad es el nombre del recurso.  
  
 Por ejemplo, el comando siguiente compila un archivo de recursos denominado StringResources.txt en StringResources.resources y genera una clase denominada `StringResources` en un archivo de código fuente de Visual Basic denominado StringResources.vb que se puede usar para tener acceso al Administrador de recursos.  
  
```console  
resgen StringResources.txt /str:vb,,StringResources   
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Recursos de aplicaciones de escritorio](../resources/index.md)
- [Crear archivos de recursos](../resources/creating-resource-files-for-desktop-apps.md)
- [Al.exe (Assembly Linker)](al-exe-assembly-linker.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
