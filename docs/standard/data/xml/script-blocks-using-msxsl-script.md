---
title: Bloques de scripts con msxsl:script
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
ms.openlocfilehash: a63452df16e452a90eff3977ac8726cc0a5ac439
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710198"
---
# <a name="script-blocks-using-msxslscript"></a>Bloques de scripts con msxsl:script
La clase <xref:System.Xml.Xsl.XslCompiledTransform> admite scripts incrustados mediante el elemento `msxsl:script`. Cuando se carga la hoja de estilos, cualquier función definida se compila en el lenguaje intermedio de Microsoft (MSIL) por medio del Code Document Object Model (CodeDOM) y se ejecutan en tiempo de ejecución. El ensamblado que se genera a partir del bloque de scripts incrustado es distinto al ensamblado que se genera para la hoja de estilos.  
  
## <a name="enable-xslt-script"></a>Cómo habilitar el script XSLT  
 La compatibilidad con scripts incrustados es un valor XSLT opcional de la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Esta compatibilidad está deshabilitada de manera predeterminada. Para habilitarla, cree un objeto <xref:System.Xml.Xsl.XsltSettings> con el conjunto de propiedades <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> establecido en `true` y pase el objeto al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
> [!NOTE]
> El script XSLT solo se debería habilitar si necesita compatibilidad con scripts o si está trabajando en un entorno de total confianza.  
  
## <a name="msxslscript-element-definition"></a>Definición del elemento msxsl:script  
 El elemento `msxsl:script` es una extensión de Microsoft de la recomendación de XSLT 1.0 y tiene la siguiente definición:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 El prefijo `msxsl` está enlazado al identificador URI del espacio de nombres `urn:schemas-microsoft-com:xslt`. La hoja de estilos debe incluir la declaración de espacio de nombres `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.  
  
 El atributo `language` es opcional. Su valor es el lenguaje de código del bloque de código incrustado. El lenguaje se asigna al compilador CodeDOM apropiado utilizando el método <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>. La clase <xref:System.Xml.Xsl.XslCompiledTransform> admite cualquier lenguaje de Microsoft .NET Framework, asumiendo que en el equipo está instalado el proveedor apropiado y está registrado en la sección system.codecom del archivo machine.config. Si no se especifica un atributo `language`, el lenguaje predeterminado es JScript. El nombre del lenguaje no distingue mayúsculas de minúsculas, por lo que 'JavaScript' y 'javascript' son equivalentes.  
  
 El atributo `implements-prefix` es obligatorio. Este atributo se utiliza para declarar un espacio de nombres y asociarlo con el bloque del script. El valor de este atributo es el prefijo que representa el espacio de nombres. Este prefijo puede definirse en cualquier parte de la hoja de estilos.  
  
> [!NOTE]
> Al utilizar el elemento `msxsl:script`, se recomienda encarecidamente que el script, independientemente del lenguaje, se coloque dentro de una sección CDATA. Puesto que el script puede contener operadores, identificadores o delimitadores para un lenguaje específico, si no está contenido en la sección CDATA, podría interpretarse erróneamente como XML. El siguiente XML muestra una plantilla de la sección CDATA en donde se puede colocar el código.  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a>Funciones del script  
 Las funciones se pueden declarar dentro del elemento `msxsl:script`. Cuando se declara una función, está contenida en un bloque de scripts. Las hojas de estilos pueden contener varios bloques de scripts que funcionan independientemente unos de otros. Esto significa que si se ejecuta código desde un bloque de scripts, no podrá llamar a una función definida en otro bloque a menos que se haya declarado en el mismo espacio de nombres y con el mismo lenguaje de scripts. Puesto que cada bloque de script puede estar en su propio lenguaje, y el bloque se analiza de acuerdo con las reglas de gramática de dicho analizador de lenguaje, se recomienda utilizar la sintaxis correcta para el lenguaje que esté siendo utilizado. Por ejemplo, si está en un bloque de scripts de Microsoft C#, utilice la sintaxis de comentarios de C#.  
  
 Los argumentos suministrados y los valores devueltos a la función pueden ser de cualquier tipo. Puesto que los tipos XPath del W3C son un subconjunto de los tipos de Common Language Runtime (CLR), la conversión de tipos tiene lugar en los tipos que no se consideran un tipo de XPath. En la siguiente tabla se muestran los tipos del W3C correspondientes y el tipo CLR equivalente.  
  
|Tipo del W3C|Tipo CLR|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 Los tipos CLR numéricos se convierten en <xref:System.Double>. El tipo <xref:System.DateTime> se convierte en <xref:System.String>. Los tipos <xref:System.Xml.XPath.IXPathNavigable> se convierten en <xref:System.Xml.XPath.XPathNavigator>. **XPathNavigator[]** se convierte en <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 El resto de los tipos inician un error.  
  
### <a name="importing-namespaces-and-assemblies"></a>Importación de espacios de nombres y ensamblajes  
 La clase <xref:System.Xml.Xsl.XslCompiledTransform> predefine un conjunto de ensamblajes y espacios de nombres que admite de manera predeterminada el elemento `msxsl:script`. Sin embargo, puede utilizar las clases y los miembros que pertenecen a un espacio de nombres que no está en la lista predefinida importando el ensamblaje y el espacio de nombres del bloque `msxsl:script`.  
  
#### <a name="assemblies"></a>Assemblies  
 Se hace referencia a los dos siguientes ensamblajes de manera predeterminada:  
  
- System.dll  
  
- System.Xml.dll  
  
- Microsoft.VisualBasic.dll (cuando el lenguaje de scripts es VB)  
  
 Puede importar los ensamblajes adicionales utilizando el elemento `msxsl:assembly`. Esto incluye el ensamblaje cuando se compila la hoja de estilos. El elemento `msxsl:assembly` tiene la siguiente definición:  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 El atributo `name` contiene el nombre del ensamblaje y el atributo `href` contiene la ruta al ensamblaje. El nombre del ensamblaje puede ser un nombre completo como, por ejemplo, "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", o un nombre corto como, por ejemplo, "System.Web".  
  
#### <a name="namespaces"></a>Espacios de nombres de  
 Los siguientes espacios de nombres están incluidos de manera predeterminada:  
  
- System  
  
- System.Collection  
  
- System.Text  
  
- System.Text.RegularExpressions  
  
- System.Xml  
  
- System.Xml.Xsl  
  
- System.Xml.Xpath  
  
- Microsoft.VisualBasic (cuando el lenguaje de scripts es VB)  
  
 Puede agregar compatibilidad para espacios de nombres adicionales utilizando el atributo `namespace`. El valor del atributo es el nombre del espacio de nombres.  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza un script incrustado para calcular la longitud de una circunferencia dado su radio.  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a>number.xml  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a>calc.xsl  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a>Resultados  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>  
```  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Generación y compilación dinámicas de código fuente](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
