---
title: "Herramienta de definici&#243;n de esquema XML (Xsd.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Herramienta de definici&#243;n de esquema XML (Xsd.exe)
La herramienta Definición de esquemas XML \(Xsd.exe\) genera clases de esquemas XML o de Common Language Runtime a partir de archivos XDR, XML y XSD, o a partir de clases de un ensamblado de motor en tiempo de ejecución.  
  
## Sintaxis  
  
```  
  
xsd file.xdr [/outputdir:directory][/parameters:file.xml]  
xsd file.xml [/outputdir:directory] [/parameters:file.xml]  
xsd file.xsd {/classes | /dataset} [/element:element]   
             [/enableLinqDataSet] [/language:language]   
                          [/namespace:namespace] [/outputdir:directory] [URI:uri]   
                          [/parameters:file.xml]  
xsd {file.dll | file.exe} [/outputdir:directory] [/type:typename [...]][/parameters:file.xml]  
```  
  
## Argumento  
  
|Argumento|Descripción|  
|---------------|-----------------|  
|*file.extension*|Especifica el archivo de entrada que se desea convertir.  La extensión debe ser alguna de las siguientes: .xdr, .xml, .xsd, .dll o .exe.<br /><br /> Si se especifica un archivo de esquema XDR \(extensión .xdr\), Xsd.exe convierte el esquema XDR en un esquema XSD.  El archivo de salida tiene el mismo nombre que el del esquema XDR, pero con la extensión .xsd.<br /><br /> Si se especifica un archivo XML \(extensión .xml\), Xsd.exe deduce, por los datos del archivo, que se trata de un esquema y genera un esquema XSD.  El archivo de salida tiene el mismo nombre que el archivo XML, pero con la extensión .xsd.<br /><br /> Si se especifica un archivo de esquema XML \(extensión .xsd\), Xsd.exe genera código fuente para objetos de motor en tiempo de ejecución que corresponden al esquema XML.<br /><br /> Si se especifica un archivo de ensamblado de motor en tiempo de ejecución \(extensión .exe o .dll\), Xsd.exe genera esquemas para uno o más tipos de ese ensamblado.  Se puede utilizar la opción **\/type** para especificar los tipos para los que se generan esquemas.  Los esquemas de salida se denominan schema0.xsd, schema1.xsd, etc.  Xsd.exe genera varios esquemas solo si los tipos dados especifican un espacio de nombres mediante el atributo personalizado **XMLRoot**.|  
  
## Opciones generales  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/h**\[**elp**\]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**\/o**\[**utputdir**\]**:***directory*|Especifica el directorio de los archivos de salida.  Este argumento sólo puede aparecer una vez.  El valor predeterminado es el directorio actual.|  
|**\/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**\/P\[arameters\]:** *file.xml*|Lee las opciones de los distintos modos de operación desde el archivo .xml especificado.  La forma abreviada es '\/p:'.  Para obtener más información, vea la sección Comentarios que se muestra más adelante.|  
  
## Opciones de archivos XSD  
 Se debe especificar sólo una de las opciones siguientes de archivos .xsd.  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/c**\[**lasses**\]|Genera clases que corresponden al esquema especificado.  Para leer datos XML del objeto, se debe utilizar el método [System.Xml.Serialization.XmlSerializer.Deserializer](frlrfSystemXmlSerializationXmlSerializerClassDeserializeTopic).|  
|**\/d**\[**ataset**\]|Genera una clase derivada de <xref:System.Data.DataSet> que corresponde al esquema especificado.  Para leer datos XML de la clase derivada, se debe utilizar el método [System.Data.DataSet.ReadXml](frlrfSystemDataDataSetClassReadXmlTopic).|  
  
 También se puede especificar cualquiera de las opciones siguientes de archivos .xsd.  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/e**\[**lement**\]**:***element*|Especifica el elemento del esquema para el que se genera código.  De forma predeterminada se escriben todos los elementos.  Este argumento se puede especificar varias veces.|  
|**\/enableDataBinding**|Implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> en todos los tipos generados para habilitar el enlace de datos.  La forma abreviada es '**\/edb**'.|  
|**\/enableLinqDataSet**|\(Forma abreviada: **\/eld**.\) Especifica que el Conjunto de datos generado se puede consultar utilizando LINQ a Conjunto de datos.  Esta opción se utiliza cuando también se especifica la opción \/dataset.  Para obtener más información, vea [Información general de LINQ to DataSet](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) y [Consultar DataSets con establecimiento de tipos](../../../docs/framework/data/adonet/querying-typed-datasets.md).  Para obtener información general acerca de la utilización de LINQ, vea [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).|  
|**\/f**\[**ields**\]|Genera campos en lugar de propiedades.  De manera predeterminada, se generan propiedades.|  
|**\/l**\[**anguage**\]**:***language*|Especifica el lenguaje de programación que se utiliza.  Se puede elegir entre **CS** \(C\#, que es el valor predeterminado\), **VB** \(Visual Basic\), **JS** \(JScript\) o **VJS** \(Visual J\#\).  También se puede especificar un nombre completo para una clase que implemente <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName>.|  
|**\/n**\[**amespace**\]**:***namespace*|Especifica el espacio de nombres del motor en tiempo de ejecución para los tipos generados.  El espacio de nombres predeterminado es **Schemas**.|  
|**\/nologo**|Suprime la pancarta.|  
|**\/order**|Genera identificadores de orden explícitos en todos los miembros de partícula.|  
|**\/o\[ut\]:** *directoryName*|Especifica el directorio de salida en el que se colocan los archivos.  El valor predeterminado es el directorio actual.|  
|**\/u**\[**ri**\]**:***uri*|Especifica el identificador URI de los elementos del esquema para el que se genera código.  Este identificador URI, si existe, se aplica a todos los elementos especificados con la opción **\/element**.|  
  
## Opciones de archivos DLL y EXE  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/t**\[**ype**\]**:***typename*|Especifica el nombre del tipo para el que se crea un esquema.  Se pueden especificar varios argumentos de tipo.  Si el argumento *typename* no especifica un espacio de nombres, Xsd.exe busca todos los tipos del ensamblado con el tipo especificado.  Si el argumento *typename* especifica un espacio de nombres, solo se busca ese tipo.  Si el argumento *typename* termina con un asterisco \(\*\), la herramienta busca todos los tipos que empiezan con la cadena que precede a este carácter.  Si se omite la opción **\/type**, Xsd.exe genera esquemas para todos los tipos del ensamblado.|  
  
## Comentarios  
 En la siguiente tabla se muestran las operaciones que realiza Xsd.exe.  
  
 XDR a XSD  
 Genera un esquema XML a partir de un archivo de esquema reducido de datos XML.  XDR es un formato de esquemas anterior basado en XML.  
  
 XML a XSD  
 Genera un esquema XML a partir de un archivo XML.  
  
 XSD a DataSet  
 Genera clases <xref:System.Data.DataSet> de Common Language Runtime a partir de un archivo de esquema XSD.  Las clases generadas proporcionan un modelo de objetos completo para datos XML regulares.  
  
 XSD a clases  
 Genera clases de motor en tiempo de ejecución a partir de un archivo de esquema XSD.  Las clases generadas se pueden usar conjuntamente con <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> para leer y escribir código XML que sigue al esquema.  
  
 Clases a XSD  
 Genera un esquema XML a partir de un tipo o tipos de un archivo de ensamblado de motor en tiempo de ejecución.  El esquema generado define el formato XML utilizado por **System.Xml.Serialization.XmlSerializer**.  
  
 Xsd.exe solo permite manipular esquemas XML que siguen al lenguaje de definición de esquemas XML \(XSD\) propuesto por el consorcio World Wide Web \(W3C\).  Para obtener más información sobre la propuesta XSD \(lenguaje de definición de esquemas XML\) o la norma XML, vea http:\/\/w3.org.  
  
## Establecer opciones con un archivo XML  
 El uso del modificador **\/parameters** permite especificar un único archivo XML que establece distintas opciones.  Las opciones que pueden establecerse dependen de la forma en que se esté utilizando la herramienta XSD.exe.  Entre estas opciones se incluyen la generación de esquemas, archivos de código o archivos de código que incluyen características **DataSet**.  Por ejemplo, el elemento **\<assembly\>** puede establecerse en el nombre de un archivo ejecutable \(.exe\) o de biblioteca de tipos \(.dll\) al generar un esquema, pero no al generar un archivo de código.  En el siguiente XML se muestra la forma de utilizar el elemento **\<generateSchemas\>** con un archivo ejecutable especificado:  
  
```  
<!-- This is in a file named GenerateSchemas.xml. -->  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateSchemas>  
   <assembly>ConsoleApplication1.exe</assembly>  
</generateSchemas>  
</xsd>  
```  
  
 Si el código XML anterior estuviese incluido en un archivo denominado GenerateSchemas.xml, habría que utilizar el modificador **\/parameters** escribiendo lo siguiente en la línea de comandos y presionando la tecla INTRO:  
  
 **xsd \/p:GenerateSchemas.xml**  
  
 Por otro lado, si se estuviese generando un esquema para un tipo único situado en el ensamblado, se podría utilizar el siguiente código XML:  
  
```  
<!-- This is in a file named GenerateSchemaFromType.xml. -->  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateSchemas>  
   <type>IDItems</type>  
</generateSchemas>  
</xsd>  
```  
  
 Pero para poder utilizar el código anterior, habría que especificar también el nombre del ensamblado en el símbolo del sistema.  Escriba lo siguiente en el símbolo del sistema \(se presupone que el nombre del archivo XML es GenerateSchemaFromType.xml\):  
  
 **xsd \/p:GenerateSchemaFromType.xml ConsoleApplication1.exe**  
  
 Solo se debe especificar una de las siguientes opciones para el elemento **\<generateSchemas\>**.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|\<assembly\>|Especifica el ensamblado a partir del cual generar el esquema.|  
|\<type\>|Especifica un tipo situado en un ensamblado para el que generar un esquema.|  
|\<xml\>|Especifica un archivo XML para el que generar un esquema.|  
|\<xdr\>|Especifica un archivo XDR para el que generar un esquema.|  
  
 Para generar un archivo de código, utilice el elemento **\<generateClasses\>**.  En el siguiente ejemplo se genera un archivo de código.  Observe que se muestran también dos atributos que permiten establecer el lenguaje de programación y el espacio de nombres del archivo generado.  
  
```  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>  
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>  
</xsd>  
<!-- You must supply an .xsd file when typing in the command line.-->  
<!-- For example: xsd /p:genClasses mySchema.xsd -->  
```  
  
 Entre las opciones que se pueden establecer para el elemento **\<generateClasses\>** se incluyen las siguientes.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|\<element\>|Especifica un elemento del archivo .xsd para el que generar código.|  
|\<schemaImporterExtensions\>|Especifica un tipo derivado de la clase <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>.|  
|\<schema\>|Especifica un archivo de esquema XML para el que generar un código.  Se pueden especificar varios archivos de esquema XML usando varios elementos de \<schema\>.|  
  
 En la siguiente tabla se muestran los atributos que también pueden utilizarse con el elemento **\<generateClasses\>**.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|lenguaje|Especifica el lenguaje de programación que se utiliza.  Se puede elegir entre **CS** \(C\#, que es el valor predeterminado\), **VB** \(Visual Basic\), **JS** \(JScript\) o **VJS** \(Visual J\#\).  También se puede especificar un nombre completo para una clase que implemente <xref:System.CodeDom.Compiler.CodeDomProvider>.|  
|namespace|Especifica el espacio de nombres del código generado.  El espacio de nombres debe ajustarse a los estándares CLR \(por ejemplo, no debe incluir espacios ni caracteres de barra diagonal inversa\).|  
|opciones|Uno de los siguientes valores: **none**, **properties** \(genera propiedades en lugar de campos públicos\), **order** o **enableDataBinding** \(vea los modificadores **\/order** y **\/enableDataBinding** en la sección Opciones de archivos XSD anterior\).|  
  
 También se puede controlar la forma en que se genera el código **DataSet** mediante el uso del elemento **\<generateDataSets\>**.  En el siguiente código XML se especifica que el código generado  ``  utiliza estructuras **DataSet** \(como la clase <xref:System.Data.DataTable>\) para crear código de Visual Basic para un elemento especificado.  Las estructuras de DataSet generadas admitirán consultas LINQ.  
  
 `\<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>`  
  
 `<generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>`  
  
 `</generateDataSet>`  
  
 `</xsd>`  
  
 Entre las opciones que se pueden establecer para el elemento **\<generateDataSet\>** se incluyen las siguientes.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|\<schema\>|Especifica un archivo de esquema XML para el que generar un código.  Se pueden especificar varios archivos de esquema XML usando varios elementos de \<schema\>.|  
  
 En la siguiente tabla se muestran los atributos que también pueden utilizarse con el elemento **\<generateDataSet\>**.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enableLinqDataSet|Especifica que el Conjunto de datos generado se puede consultar utilizando LINQ a Conjunto de datos.  El valor predeterminado es false.|  
|lenguaje|Especifica el lenguaje de programación que se utiliza.  Se puede elegir entre **CS** \(C\#, que es el valor predeterminado\), **VB** \(Visual Basic\), **JS** \(JScript\) o **VJS** \(Visual J\#\).  También se puede especificar un nombre completo para una clase que implemente <xref:System.CodeDom.Compiler.CodeDomProvider>.|  
|namespace|Especifica el espacio de nombres del código generado.  El espacio de nombres debe ajustarse a los estándares CLR \(por ejemplo, no debe incluir espacios ni caracteres de barra diagonal inversa\).|  
  
 Hay atributos que pueden establecerse en el elemento **\<xsd\>** de nivel superior.  Estas opciones pueden utilizarse con cualquiera de los elementos secundarios \(**\<generateSchemas\>\<generateClasses\>, \<generateDataSet\>** o \).  El siguiente código XML genera código para un elemento denominado "IDItems" del directorio de resultados denominado "MyOutputDirectory".  
  
```  
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>  
<generateClasses>  
<element>IDItems</element>  
</generateClasses>  
</xsd>  
```  
  
 En la siguiente tabla se muestran los atributos que también pueden utilizarse con el elemento **\<xsd\>**.  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|resultado|Nombre del directorio donde se colocará el esquema o archivo de código generado.|  
|nologo|Suprime la pancarta.  Se establece en **true** o **false**.|  
|ayuda|Muestra las opciones y la sintaxis de los comandos para la herramienta.  Se establece en **true** o **false**.|  
  
```  
  
```  
  
## Ejemplos  
 El comando siguiente genera un esquema XML a partir de `myFile.xdr` y lo guarda en el directorio actual.  
  
```  
xsd myFile.xdr   
```  
  
 El comando siguiente genera un esquema XML a partir de `myFile.xml` y lo guarda en el directorio especificado.  
  
```  
xsd myFile.xml /outputdir:myOutputDir  
```  
  
 El siguiente comando genera un conjunto de datos correspondiente al esquema especificado en el lenguaje C\# y guarda estos datos como `XSDSchemaFile.cs` en el directorio actual.  
  
```  
xsd /dataset /language:CS XSDSchemaFile.xsd  
```  
  
 El comando siguiente genera esquemas XML para todos los tipos del ensamblado `myAssembly.dll`, y los guarda como `schema0.xsd` en el directorio actual.  
  
```  
xsd myAssembly.dll    
```  
  
## Vea también  
 <xref:System.Data.DataSet>   
 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>   
 [Tools](../../../docs/framework/tools/index.md)   
 [System.Xml.Serialization.XmlSerializer.Deserializer](frlrfSystemXmlSerializationXmlSerializerClassDeserializeTopic)   
 [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)   
 [Información general de LINQ to DataSet](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)   
 [Consultar DataSets con establecimiento de tipos](../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)