---
title: (Visual Basic) de nombres de elementos declarados | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 56ac0684e5176f33aa6f9600f20d9fe3fcf09416
ms.lasthandoff: 03/13/2017

---
# <a name="declared-element-names-visual-basic"></a>Nombres de elementos declarados (Visual Basic)
Cada elemento declarado tiene un nombre, también denominado una *identificador*, que es lo que el código que se utiliza para hacer referencia a él.  
  
## <a name="rules"></a>Reglas  
 Nombre de elemento en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] debe observar las reglas siguientes:  
  
-   Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).  
  
-   Sólo debe contener caracteres alfabéticos, dígitos decimales y caracteres de subrayado.  
  
-   Debe contener al menos un carácter alfabético o un dígito decimal si empieza con un carácter de subrayado.  
  
-   No debe ser superior a 1023 caracteres de largo.  
  
 El límite de longitud de 1023 caracteres también se aplica a toda la cadena de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 El ejemplo siguiente muestra algunos nombres de elemento válido.  
  
 `aB123__45`  
  
 `_567`  
  
 El ejemplo siguiente muestra algunos nombres de elemento no válido. El primero contiene sólo un carácter de subrayado, el segundo comienza con un dígito decimal y el tercero contiene un carácter no válido ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Los nombres de elemento a partir de un carácter de subrayado (`_`) no forman parte de la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que define dichos nombres. Sin embargo, un carácter de subrayado en cualquier otra posición de un nombre de elemento es conforme a CLS.  
  
### <a name="name-length-guidelines"></a>Directrices de longitud de nombre  
 A efectos prácticos, su nombre debe ser lo más corto posible al identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce el tamaño de línea de longitud y el archivo de código fuente.  
  
 Por otro lado, su nombre no debe ser tan corto que no adecuadamente describe lo que representa el elemento y cómo lo utiliza el código. Esto es importante para la legibilidad del código. Si alguien intenta entenderlo o si usted busca lo mucho tiempo después de que lo escribió, nombres de elementos adecuados pueden guardar una cantidad considerable de tiempo.  
  
## <a name="escaped-names"></a>Nombres de escape  
 Por lo general, un nombre de elemento no debe coincidir con cualquiera de las palabras clave reservadas por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], como `Case` o `Friend`. Sin embargo, puede definir un *nombre con escape*, que está incluido entre corchetes (`[ ]`). Un nombre con escape puede coincidir con cualquier [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] (palabra clave), puesto que los corchetes eliminan toda ambigüedad posible. Utiliza también los corchetes al hacer referencia al nombre más adelante en el código.  
  
 En general, debe utilizar nombres de escape sólo cuando:  
  
-   Su código ha migrado desde una versión anterior de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] que no reservó la palabra clave que se va a usar como nombre; o  
  
-   Está trabajando con código escrito en otro idioma en el que la palabra clave determinada no está reservada.  
  
 De lo contrario, considere cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave. El entorno de desarrollo integrado (IDE) proporciona una manera fácil de hacerlo. Para obtener más información, consulte [refactorización](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Mayúsculas y minúsculas en nombres  
 Los nombres de elemento en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] distinguen mayúsculas de minúsculas. Esto significa que cuando el compilador compara dos nombres que difieran en mayúsculas o minúsculas, los interpreta como el mismo nombre. Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.  
  
 Sin embargo, common language runtime (CLR) usa el enlace entre mayúsculas y minúsculas. Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas. Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`. Si posteriormente vuelve a compilar la clase y cambia el nombre del elemento a `abc`, los otros ensamblados que utilicen la clase ya no pueden tener acceso a ese elemento. Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.  
  
## <a name="names-and-locales"></a>Nombres y configuraciones regionales  
 Comparación de nombres es independiente de la configuración regional. Si dos nombres coinciden en una configuración regional, se garantiza que coincidirán en todas las configuraciones regionales.  
  
## <a name="see-also"></a>Vea también  
 [Elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)
