---
title: "Nombres de elementos declarados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "caracteres de escape [] [Visual Basic]"
  - "distinción de mayúsculas y minúsculas, nombres de elementos declarados"
  - "instrucciones de declaración, elementos declarados"
  - "declaraciones, elementos"
  - "elementos declarados, acerca de los elementos declarados"
  - "elementos declarados, distinción de mayúsculas y minúsculas"
  - "elementos declarados, identificadores"
  - "elementos declarados, nombres"
  - "elementos declarados, nombres válidos"
  - "declarar elementos"
  - "nombres de elementos"
  - "caracteres de escape"
  - "nombres de escape"
  - "identificadores, elementos declarados"
  - "identificadores, elementos"
  - "nombres, elementos declarados"
  - "nombres, elementos"
  - "nombres, convenciones de nomenclatura"
  - "nombres, reglas de Visual Basic"
  - "convenciones de nomenclatura"
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Nombres de elementos declarados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Todo elemento declarado tiene un nombre, también denominado *identificador*, que utiliza el código para hacer referencia a él.  
  
## Reglas  
 Un nombre de elemento en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe observar las reglas siguientes:  
  
-   Debe comenzar por un carácter alfabético o un signo de subrayado \(`_`\).  
  
-   Sólo puede contener caracteres alfabéticos, dígitos decimales y signos de subrayado.  
  
-   Debe contener por lo menos un carácter alfabético o un dígito decimal, si empieza con un signo de subrayado.  
  
-   No puede superar los 1023 caracteres de longitud.  
  
 El límite de longitud de 1023 caracteres también se aplica a la cadena completa de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 El ejemplo siguiente muestra algunos nombres de elementos válidos.  
  
 `aB123__45`  
  
 `_567`  
  
 El ejemplo siguiente muestra algunos nombres de elementos no válidos.  El primero contiene sólo un subrayado, el segundo comienza con un dígito decimal y el tercero contiene un carácter no válido \($\).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Los nombres de elementos que empiezan por un carácter de subrayado \(`_`\) no forman parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\); por tanto, el código conforme a CLS no puede usar ningún componente que defina tales nombres.  Sin embargo, un carácter de subrayado en cualquier otra posición de un nombre de elemento es conforme a CLS.  
  
### Directrices sobre longitud de nombres  
 A efectos prácticos, su nombre debe ser tan corto como sea posible aunque tiene que identificar claramente la naturaleza del elemento.  Esto mejora la legibilidad de su código y reduce la longitud de línea y el tamaño del archivo de origen.  
  
 Por otro lado, su nombre no debe ser tan corto que no describa lo que el elemento representa adecuadamente y cómo lo utiliza el código.  Esto es importante para la legibilidad del código.  Si alguien más lo intenta entender o si el propio usuario lo examina después de mucho tiempo de haberlo escrito, unos nombres de elementos adecuados pueden ahorrar mucho tiempo.  
  
## Nombres con escape  
 En general, el nombre de un elemento no puede coincidir con ninguna de las palabras clave reservadas para [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], como `Case` o `Friend`.  No obstante, puede definir un *nombre con escape* que se especifica incluido entre corchetes \(`[ ]`\).  Un nombre con escape puede coincidir con cualquier palabra clave de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], puesto que los corchetes quitan toda ambigüedad posible.  También puede usar los corchetes en las referencias al nombre en el código.  
  
 En general, sólo debe utilizar los nombres con escape cuando:  
  
-   Su código ha migrado de una versión anterior de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] que no reservó la palabra clave que está utilizando como nombre; o  
  
-   Está trabajando con código escrito en otro lenguaje en el que la palabra clave determinada no está reservada.  
  
 De lo contrario, debe considerar cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave.  El entorno de desarrollo integrado \(IDE\) proporciona una manera fácil de hacer esto.  Para obtener más información, vea [Refactorización y Cambiar nombre \(Cuadro de diálogo\)](../../../../visual-basic/developing-apps/using-ide/refactoring-and-rename-dialog-box.md).  
  
## Distinguir mayúsculas de minúsculas en los nombres  
 Los nombres de elementos en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no distinguen entre mayúsculas y minúsculas.  Es decir, cuando el compilador compara dos nombres cuya única diferencia está en letras mayúsculas o minúsculas, los interpreta como el mismo nombre.  Por ejemplo, `ABC` y `abc` hacen referencia al mismo elemento declarado.  
  
 No obstante, Common Language Runtime \(CLR\) utiliza enlaces que sí tienen en cuenta esta distinción.  Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres sí se distinguirán por sus mayúsculas o minúsculas.  Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados utilizan la clase por medio de Common Language Runtime, deberán hacer referencia al elemento como `ABC`.  Si, posteriormente, vuelve a compilar la clase y cambia el nombre del elemento a `abc`, los otros ensamblados que utilicen la clase ya no tendrán acceso a este elemento.  Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.  
  
## Nombres y configuraciones regionales  
 La comparación de nombres es independiente de la configuración regional.  Si dos nombres coinciden en una configuración regional, se garantiza que coincidirán en todas las configuraciones regionales.  
  
## Vea también  
 [Elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)