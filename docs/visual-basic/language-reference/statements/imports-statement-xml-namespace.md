---
title: "Imports (Instrucci&#243;n, Espacio de nombres XML) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ImportsXmlns"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "importaciones [Visual Basic]"
  - "Imports (instrucción) [Visual Basic]"
  - "espacios de nombres [Visual Basic], importar"
  - "espacio de nombres XML [Visual Basic], importar"
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Imports (Instrucci&#243;n, Espacio de nombres XML)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Importa los prefijos del espacio de nombres XML para su uso en literales XML y propiedades de eje XML.  
  
## Sintaxis  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## Elementos  
 `xmlNamespacePrefix`  
 Opcional.  Cadena por la que los elementos y atributos XML pueden hacer referencia a `xmlNamespaceName`.  Si no se proporciona `xmlNamespacePrefix`, el espacio de nombres XML importado es el espacio de nombres XML predeterminado.  Debe ser un identificador XML válido.  Para obtener más información, vea [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Obligatorio.  Cadena que identifica el espacio de nombres XML que se importa.  
  
## Comentarios  
 Puede usar la instrucción `Imports` para definir espacios de nombres XML globales que puede utilizar con literales XML y propiedades de eje XML o como los parámetros pasados al operador `GetXmlNamespace`.  \(Para obtener información sobre cómo utilizar la instrucción `Imports` con el fin de importar un alias que se pueda usar donde los nombres de tipo se utilizan en el código, vea [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).\) La sintaxis para declarar un espacio de nombres XML utilizando la instrucción `Imports` es idéntica a la sintaxis usada en XML.  Por consiguiente, puede copiar una declaración de espacio de nombres de un archivo XML y usarla en una instrucción `Imports`.  
  
 Los prefijos de espacios de nombres XML son útiles si desea crear repetidamente elementos XML cuyo origen sea el mismo espacio de nombres.  El prefijo del espacio de nombres XML declarado con la instrucción `Imports` es global en tanto que todo el código del archivo puede disponer de él.  Puede usarlo si crea literales de elemento XML y al tener acceso a las propiedades de eje XML.  Para obtener más información, vea [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Si define un espacio de nombres XML global sin ningún prefijo de espacio de nombres \(por ejemplo, `Imports <xmlns="http://SomeNameSpace>"`\), ese espacio de nombres se considera el espacio de nombres XML predeterminado.  El espacio de nombres XML predeterminado se utiliza para cualquier literal de elemento XML o propiedades de eje de atributo XML que no especifiquen explícitamente un espacio de nombres.  El espacio de nombres predeterminado también se usa si el espacio de nombres especificado es el espacio de nombres vacío \(es decir, `xmlns=""`\).  El espacio de nombres XML predeterminado no se aplica a los atributos XML de literales XML ni a las propiedades de eje de atributo XML que no tengan espacio de nombres.  
  
 Los espacios de nombres XML definidos en un literal XML, que se denomina *espacios de nombres XML locales*, tienen prioridad sobre los espacios de nombres XML que define la instrucción `Imports` como globales.  Los espacios de nombres XML que define la instrucción `Imports` tienen prioridad sobre los espacios de nombres XML importados para un proyecto de Visual Basic.  Si un literal XML define un espacio de nombres XML, ese espacio de nombres local no se aplica a las expresiones incrustadas.  
  
 Los espacios de nombres XML globales siguen las mismas reglas de ámbito y definición que los espacios de nombres de .NET Framework.  Como resultado, puede incluir una instrucción `Imports` para definir un espacio de nombres XML global donde pueda importar un espacio de nombres de .NET Framework.  Se incluyen tanto los archivos de código como los espacios de nombres importados de nivel de proyecto.  Para obtener información sobre espacios de nombres importados de nivel de proyecto, vea [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 Cada archivo de código fuente puede contener cualquier número de instrucciones `Imports`.  Éstas deben ir a continuación de las declaraciones de opción, como la instrucción `Option Strict`, y deben preceder a cualquier declaración de elemento de programación como las instrucciones `Module` o `Class`.  
  
## Ejemplo  
 El ejemplo siguiente importa un espacio de nombres XML predeterminado y un espacio de nombres XML identificado con el prefijo `ns`.  Después crea literales XML que utilizan ambos espacios de nombres.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 Este código muestra el texto siguiente:  
  
```  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## Ejemplo  
 El ejemplo siguiente importa el prefijo de espacio de nombres XML `ns`.  Después crea un literal XML que usa el prefijo de espacio de nombres y muestra el formato final del elemento.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Este código muestra el texto siguiente:  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Observe que el compilador convirtió el prefijo del espacio de nombres XML de un prefijo global en una definición de prefijo local.  
  
## Ejemplo  
 El ejemplo siguiente importa el prefijo de espacio de nombres XML `ns`.  A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Patrick Hines`  
  
## Vea también  
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [GetXmlNamespace \(Operador\)](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)