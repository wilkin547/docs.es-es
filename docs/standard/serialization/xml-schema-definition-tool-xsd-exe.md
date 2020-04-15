---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: 6ec99e77db4215184547ea2bbbe0d1ff8ad3c286
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389772"
---
# <a name="xml-schema-definition-tool-xsdexe"></a>XML Schema Definition Tool (Xsd.exe)

La herramienta Definición de esquemas XML (Xsd.exe) genera clases de esquemas XML o de Common Language Runtime a partir de archivos XDR, XML y XSD, o a partir de clases de un ensamblado de motor en tiempo de ejecución.

La herramienta Dedefinición de esquemas XML (Xsd.exe) normalmente se puede encontrar en la siguiente ruta de acceso:
_C:\\Archivos de programa\\(x86)\\\\Microsoft SDKs Windows .\\\\\\_

## <a name="syntax"></a>Sintaxis

Ejecute la herramienta desde la línea de comandos.

```console
xsd file.xdr [-outputdir:directory][/parameters:file.xml]
xsd file.xml [-outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [-outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [-outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```
  
> [!TIP]
> Para que las herramientas de .NET `Path`Framework `Include`funcionen correctamente, debe establecer correctamente las variables , y `Lib` el entorno. Establezca estas variables de entorno ejecutando SDKVars.bat, que se encuentra en el directorio \<SDK>\v2.0\Bin. SDKVars.bat debe ejecutarse en cada shell de comando.

## <a name="argument"></a>Argumento

|Argumento|Descripción|
|--------------|-----------------|
|*file.extension*|Especifica el archivo de entrada que se desea convertir. Debe especificar la extensión como una de las siguientes opciones: .xdr, .xml, .xsd, .dll o .exe.<br /><br /> Si se especifica un archivo de esquema XDR (extensión .xdr), Xsd.exe convierte el esquema XDR en un esquema XSD. El archivo de salida tiene el mismo nombre que el del esquema XDR, pero con la extensión .xsd.<br /><br /> Si se especifica un archivo XML (extensión .xml), Xsd.exe deduce, por los datos del archivo, que se trata de un esquema y genera un esquema XSD. El archivo de salida tiene el mismo nombre que el archivo XML, pero con la extensión .xsd.<br /><br /> Si se especifica un archivo de esquema XML (extensión .xsd), Xsd.exe genera código fuente para objetos de motor en tiempo de ejecución que corresponden al esquema XML.<br /><br /> Si se especifica un archivo de ensamblado de motor en tiempo de ejecución (extensión .exe o .dll), Xsd.exe genera esquemas para uno o más tipos de ese ensamblado. Se puede utilizar la opción `/type` para especificar los tipos para los que se generan esquemas. Los esquemas de salida se denominan schema0.xsd, schema1.xsd, etc. Xsd.exe genera varios esquemas solo si los tipos dados especifican un espacio de nombres mediante el atributo personalizado `XMLRoot`.|

## <a name="general-options"></a>Opciones generales

|Opción|Descripción|
|------------|-----------------|
|**/h\[elp\]**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|**/o\[\]utputdir :**_directorio_|Especifica el directorio de los archivos de salida. Este argumento sólo puede aparecer una vez. El valor predeterminado es el directorio actual.|
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|**/p\[arameters\]:**_file.xml_|Lee las opciones de los distintos modos de operación desde el archivo .xml especificado. La forma abreviada es `/p:`. Para obtener más información, consulte la sección [Comentarios.](#remarks)|

## <a name="xsd-file-options"></a>Opciones de archivos XSD
 Se debe especificar sólo una de las opciones siguientes de archivos .xsd.

|Opción|Descripción|
|------------|-----------------|
|**/c\[lasses\]**|Genera clases que corresponden al esquema especificado. Para leer datos XML del objeto, use el método <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType>.|
|**/d\[ataset\]**|Genera una clase derivada de <xref:System.Data.DataSet> que corresponde al esquema especificado. Para leer datos XML de la clase derivada, use el método <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType>.|

 También se puede especificar cualquiera de las opciones siguientes de archivos .xsd.

|Opción|Descripción|
|------------|-----------------|
|**/e\[\]lement :**_elemento_|Especifica el elemento del esquema para el que se genera código. De forma predeterminada se escriben todos los elementos. Este argumento se puede especificar varias veces.|
|**/enableDataBinding**|Implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> en todos los tipos generados para habilitar el enlace de datos. La forma abreviada es `/edb`.|
|**/enableLinqDataSet**|(Forma corta: `/eld`.) Especifica que el DataSet generado se puede consultar mediante LINQ to DataSet. Esta opción se utiliza cuando también se especifica la opción /dataset. Para más información, vea [LINQ to DataSet Overview (Información general sobre LINQ to DataSet)](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) y [Querying Typed DataSets (Consultar objetos DataSet con tipo)](../../../docs/framework/data/adonet/querying-typed-datasets.md). Para obtener información general sobre el uso de LINQ, vea Consulta integrada de lenguaje [(LINQ) - C-](../../csharp/programming-guide/concepts/linq/index.md) o Consulta integrada de lenguaje [(LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).|
|**/f\[ields\]**|Genera campos en lugar de propiedades. De manera predeterminada, se generan propiedades.|
|**/l\[\]anguage :**_idioma_|Especifica el lenguaje de programación que se utiliza. Se puede elegir entre `CS` (C#, que es el valor predeterminado), `VB` (Visual Basic), `JS` (JScript) o `VJS` (Visual J#). También se puede especificar un nombre completo para una clase que implemente <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.|
|**/n\[\]amespace :** espacio de_nombres_|Especifica el espacio de nombres del motor en tiempo de ejecución para los tipos generados. El espacio de nombres predeterminado es `Schemas`.|
|**/nologo**|Suprime la pancarta.|
|**/orden**|Genera identificadores de orden explícitos en todos los miembros de partícula.|
|**/o\[\]ut :**_directoryName_|Especifica el directorio de salida en el que se colocan los archivos. El valor predeterminado es el directorio actual.|
|**/u\[\]ri :**_uri_|Especifica el identificador URI de los elementos del esquema para el que se genera código. Este identificador URI, si existe, se aplica a todos los elementos especificados con la opción `/element`.|

## <a name="dll-and-exe-file-options"></a>Opciones de archivos DLL y EXE

|Opción|Descripción|
|------------|-----------------|
|**/t\[ype\]:** nombre de_tipo_|Especifica el nombre del tipo para el que se crea un esquema. Se pueden especificar varios argumentos de tipo. Si *typename* no especifica un espacio de nombres, Xsd.exe busca todos los tipos del ensamblado con el tipo especificado. Si *typename* especifica un espacio de nombres, solo se busca ese tipo. Si *typename* termina con carácter de asterisco (\*), la herramienta busca todos los tipos que empiezan con la cadena anterior a \*. Si se omite la opción `/type`, Xsd.exe genera esquemas para todos los tipos del ensamblado.|

## <a name="remarks"></a>Observaciones

En la siguiente tabla se muestran las operaciones que realiza Xsd.exe.

| | |
|------------|-----------------|
|XDR a XSD|Genera un esquema XML a partir de un archivo de esquema reducido de datos XML. XDR es un formato de esquemas anterior basado en XML.|
|XML a XSD|Genera un esquema XML a partir de un archivo XML.|
|XSD a DataSet|Genera clases <xref:System.Data.DataSet> de Common Language Runtime a partir de un archivo de esquema XSD. Las clases generadas proporcionan un modelo de objetos completo para datos XML regulares.|
|XSD a clases|Genera clases de motor en tiempo de ejecución a partir de un archivo de esquema XSD. Las clases generadas se pueden usar conjuntamente con <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> para leer y escribir código XML que sigue al esquema.|
|Clases a XSD| Genera un esquema XML a partir de un tipo o tipos de un archivo de ensamblado de motor en tiempo de ejecución. El esquema generado define el formato <xref:System.Xml.Serialization.XmlSerializer>XML utilizado por el archivo .|

 Xsd.exe solo permite manipular esquemas XML que siguen al lenguaje de definición de esquemas XML (XSD) propuesto por el consorcio World Wide Web (W3C). Para obtener más información sobre la propuesta de <https://w3.org>definición de esquemas XML o el estándar XML, consulte .

## <a name="setting-options-with-an-xml-file"></a>Establecer opciones con un archivo XML

El uso del modificador `/parameters` permite especificar un único archivo XML que establece distintas opciones. Las opciones que pueden establecerse dependen de la forma en que se esté utilizando la herramienta XSD.exe. Entre estas opciones se incluyen la generación de esquemas, archivos de código o archivos de código que incluyen características `DataSet`. Por ejemplo, el elemento `<assembly>` puede establecerse en el nombre de un archivo ejecutable (.exe) o de biblioteca de tipos (.dll) al generar un esquema, pero no al generar un archivo de código. En el siguiente XML se muestra la forma de utilizar el elemento `<generateSchemas>` con un archivo ejecutable especificado:

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

Si el XML anterior está contenido en un archivo denominado GenerateSchemas.xml, utilice el `/parameters` modificador escribiendo lo siguiente en un símbolo del sistema y presionando **Intro:**

```console
 xsd /p:GenerateSchemas.xml
```

Por otro lado, si se estuviese generando un esquema para un tipo único situado en el ensamblado, se podría utilizar el siguiente código XML:

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

Pero para poder utilizar el código anterior, habría que especificar también el nombre del ensamblado en el símbolo del sistema. Escriba lo siguiente en un símbolo del sistema (presumiendo que el archivo XML se denomina GenerateSchemaFromType.xml):

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

Solo se debe especificar una de las siguientes opciones para el elemento `<generateSchemas>`.

|Elemento|Descripción|
|-------------|-----------------|
|\<assembly>|Especifica el ensamblado a partir del cual generar el esquema.|
|\<type>|Especifica un tipo situado en un ensamblado para el que generar un esquema.|
|\<xml>|Especifica un archivo XML para el que generar un esquema.|
|\<xdr>|Especifica un archivo XDR para el que generar un esquema.|

Para generar un archivo de código, utilice el elemento `<generateClasses>`. En el siguiente ejemplo se genera un archivo de código. Observe que se muestran también dos atributos que permiten establecer el lenguaje de programación y el espacio de nombres del archivo generado.

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 Entre las opciones que se pueden establecer para el elemento `<generateClasses>` se incluyen las siguientes.

|Elemento|Descripción|
|-------------|-----------------|
|\<element>|Especifica un elemento del archivo .xsd para el que generar código.|
|\<schemaImporterExtensions>|Especifica un tipo derivado de la clase <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>.|
|\<schema>|Especifica un archivo de esquema XML para el que generar un código. Se pueden especificar varios archivos de esquema XML con varios elementos \<schema>.|

En la siguiente tabla se muestran los atributos que también pueden utilizarse con el elemento `<generateClasses>`.

|Atributo|Descripción|
|---------------|-----------------|
|language|Especifica el lenguaje de programación que se utiliza. Se puede elegir entre `CS` (C#, que es el valor predeterminado), `VB` (Visual Basic), `JS` (JScript) o `VJS` (Visual J#). También se puede especificar un nombre completo para una clase que implemente <xref:System.CodeDom.Compiler.CodeDomProvider>.|
|espacio de nombres|Especifica el espacio de nombres del código generado. El espacio de nombres debe ajustarse a los estándares CLR (por ejemplo, no debe incluir espacios ni caracteres de barra diagonal inversa).|
|opciones|Uno de los siguientes valores: `none`, `properties` (genera propiedades en lugar de campos públicos), `order` o `enableDataBinding` (vea los modificadores `/order` y `/enableDataBinding` en la sección Opciones de archivos XSD anterior).|

 También se puede controlar la forma en que se genera el código `DataSet` mediante el uso del elemento `<generateDataSet>`. El siguiente XML especifica que el `DataSet` código generado utiliza <xref:System.Data.DataTable> estructuras (como la clase) para crear código de Visual Basic para un elemento especificado. Las estructuras de DataSet generadas admitirán consultas LINQ.

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

Entre las opciones que se pueden establecer para el elemento `<generateDataSet>` se incluyen las siguientes.

|Elemento|Descripción|
|-------------|-----------------|
|\<schema>|Especifica un archivo de esquema XML para el que generar un código. Se pueden especificar varios archivos de esquema XML con varios elementos \<schema>.|

 En la siguiente tabla se muestran los atributos que también pueden utilizarse con el elemento `<generateDataSet>`.

|Atributo|Descripción|
|---------------|-----------------|
|enableLinqDataSet|Especifica que el Conjunto de datos generado se puede consultar utilizando LINQ a Conjunto de datos. El valor predeterminado es false.|
|language|Especifica el lenguaje de programación que se utiliza. Se puede elegir entre `CS` (C#, que es el valor predeterminado), `VB` (Visual Basic), `JS` (JScript) o `VJS` (Visual J#). También se puede especificar un nombre completo para una clase que implemente <xref:System.CodeDom.Compiler.CodeDomProvider>.|
|espacio de nombres|Especifica el espacio de nombres del código generado. El espacio de nombres debe ajustarse a los estándares CLR (por ejemplo, no debe incluir espacios ni caracteres de barra diagonal inversa).|

 Hay atributos que pueden establecerse en el elemento `<xsd>` de nivel superior. Estas opciones pueden utilizarse con cualquiera de los elementos secundarios (`<generateSchemas>` o ). El siguiente código XML genera código para un elemento denominado "IDItems" del directorio de resultados denominado "MyOutputDirectory".

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

En la siguiente tabla se muestran los atributos que también pueden utilizarse con el elemento `<xsd>`.

|Atributo|Descripción|
|---------------|-----------------|
|output|Nombre del directorio donde se colocará el esquema o archivo de código generado.|
|nologo|Suprime la pancarta. Se establece en `true` o `false`.|
|help|Muestra las opciones y la sintaxis de los comandos para la herramienta. Se establece en `true` o `false`.|

## <a name="examples"></a>Ejemplos
 El comando siguiente genera un esquema XML a partir de `myFile.xdr` y lo guarda en el directorio actual.

```console
xsd myFile.xdr
```

El comando siguiente genera un esquema XML a partir de `myFile.xml` y lo guarda en el directorio especificado.

```console
xsd myFile.xml /outputdir:myOutputDir
```

El siguiente comando genera un conjunto de datos correspondiente al esquema especificado en el lenguaje C# y guarda estos datos como `XSDSchemaFile.cs` en el directorio actual.

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

El comando siguiente genera esquemas XML para todos los tipos del ensamblado `myAssembly.dll`, y los guarda como `schema0.xsd` en el directorio actual.

```console
xsd myAssembly.dll
```

## <a name="see-also"></a>Vea también

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [Herramientas](../../../docs/framework/tools/index.md)
- [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [Información general de LINQ to DataSet](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [Consultar objetos DataSet con tipo](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [LINQ (Consulta integrada en el lenguaje) (C-)](../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ (consulta integrada en lenguaje) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/index.md)
