---
title: "Procesar el archivo XML (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML [C#], procesar"
  - "procesamiento de XML [C#]"
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Procesar el archivo XML (Gu&#237;a de programaci&#243;n de C#)
El compilador genera una cadena id. por cada construcción del código marcada para generar documentación.  \(Para obtener información sobre cómo etiquetar el código, vea [Etiquetas recomendadas para comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)\). La cadena id. identifica de forma exclusiva cada construcción.  Los programas que procesan el archivo XML pueden utilizar la cadena id. para identificar el correspondiente elemento de metadatos\/reflexión de .NET Framework al que se aplica la documentación.  
  
 El archivo XML no es una representación jerárquica del código, es una lista plana que tiene un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas id.:  
  
-   No hay ningún espacio en blanco en la cadena.  
  
-   La primera parte de la cadena id. identifica el tipo de miembro por medio de un único carácter seguido de dos puntos.  Se utilizan los siguientes tipos de miembros:  
  
    |Carácter|Descripción|  
    |--------------|-----------------|  
    |N|Espacio de nombres<br /><br /> No se pueden agregar comentarios de documentación a un espacio de nombres, pero se pueden hacer referencias cref a ellos donde se admitan.|  
    |T|tipo: class, interface, struct, enum, delegate|  
    |F|campo|  
    |P|propiedad \(incluidos indizadores u otras propiedades indizadas\)|  
    |M|método \(incluidos métodos especiales como constructores, operadores, etc.\)|  
    |E|event|  
    |\!|cadena de error<br /><br /> El resto de la cadena proporciona información acerca del error.  El compilador de C\# genera información de error para vínculos que no se pueden resolver.|  
  
-   La segunda parte de la cadena es el nombre completo del elemento, empezando en la raíz del espacio de nombres.  El nombre del elemento, los tipos contenedores y el espacio de nombres se separan mediante puntos.  Si el propio nombre del elemento contiene puntos, éstos se reemplazan por el signo \#.  Se supone que ningún elemento contiene un signo \# directamente en su nombre.  Por ejemplo, el nombre completo del constructor de String sería "System.String.\#ctor".  
  
-   Para propiedades y métodos, si existen argumentos para el método, la lista de argumentos que se encuentra entre paréntesis aparece a continuación.  Si no existen argumentos, no se escribe ningún paréntesis.  Los argumentos se separan por comas.  La codificación de cada argumento indica directamente cómo se codifica en una firma de .NET Framework:  
  
    -   Tipos base.  Los tipos normales \(ELEMENT\_TYPE\_CLASS o ELEMENT\_TYPE\_VALUETYPE\) se representan como el nombre completo del tipo.  
  
    -   Tipos intrínsecos \(por ejemplo, ELEMENT\_TYPE\_I4, ELEMENT\_TYPE\_OBJECT, ELEMENT\_TYPE\_STRING, ELEMENT\_TYPE\_TYPEDBYREF.  y ELEMENT\_TYPE\_VOID\) se representan como el nombre completo del tipo completo correspondiente.  Por ejemplo, System.Int32 o System.TypedReference.  
  
    -   ELEMENT\_TYPE\_PTR se representa con un '\*' a continuación del tipo modificado.  
  
    -   ELEMENT\_TYPE\_BYREF se representa con un signo '@' a continuación del tipo modificado.  
  
    -   ELEMENT\_TYPE\_PINNED se representa con un signo '^' a continuación del tipo modificado.  El compilador de C\# nunca genera este resultado.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ se representa como una '&#124;' y el nombre completo de la clase modificadora, a continuación del tipo modificado.  El compilador de C\# nunca genera este resultado.  
  
    -   ELEMENT\_TYPE\_CMOD\_OPT se representa como '\!' y el nombre completo de la clase modificadora, a continuación del tipo modificado.  
  
    -   ELEMENT\_TYPE\_SZARRAY se representa como "\[\]" a continuación del tipo de elemento de la matriz.  
  
    -   ELEMENT\_TYPE\_GENERICARRAY se representa como "\[?\]" a continuación del tipo de elemento de la matriz.  El compilador de C\# nunca genera este resultado.  
  
    -   ELEMENT\_TYPE\_ARRAY se representa como \[*límite inferior*:`size`,*límite inferior*:`size`\] donde el número de comas es el rango, 1, y los límites inferiores y el tamaño de cada dimensión, si se conocen, se representan en decimal.  Si no se especifica un límite inferior ni un tamaño, simplemente se omite.  Si el límite inferior y el tamaño de una dimensión particular se omiten, el signo ':' también se omite.  Por ejemplo, una matriz de dos dimensiones con 1 como límites inferiores y sin tamaños especificados se representa como \[1:,1:\].  
  
    -   ELEMENT\_TYPE\_FNPTR se representa como "\=FUNC:`type` \(*firma*\)", donde `type` es el tipo de valor devuelto y *firma* corresponde a los argumentos del método.  Si no existen argumentos, los paréntesis se omiten.  El compilador de C\# nunca genera este resultado.  
  
     Los siguientes componentes de una firma no se representan porque nunca se utilizan para diferenciar métodos sobrecargados:  
  
    -   convención de llamadas  
  
    -   tipo de valor devuelto  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   Sólo para operadores de conversión \(op\_Implicit y op\_Explicit\), el valor devuelto del método se codifica como un signo '~' seguido del tipo de valor devuelto.  
  
-   En los tipos genéricos, el nombre del tipo va seguido de un acento invertido y de un número que indica el número de parámetros de tipo genérico.  Por ejemplo,  
  
     `<member name="T:SampleClass`2">` es la etiqueta para un tipo definido como `public class SampleClass\<T, U>`.  
  
     Para métodos que toman tipos genéricos como parámetros, los parámetros de tipo genérico se especifican como números con un acento invertido antepuesto \(por ejemplo \`0, \`1\).  Cada número representa una notación de matrices basada en cero en los parámetros genéricos del tipo.  
  
## Ejemplos  
 Los siguientes ejemplos muestran cómo se generarían las cadenas de id. para una clase y sus miembros:  
  
 [!code-cs[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#21)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)