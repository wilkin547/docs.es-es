---
title: Nombres de elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814073"
---
# <a name="declared-element-names-visual-basic"></a>Nombres de elementos declarados (Visual Basic)
Cada elemento declarado tiene un nombre, también denominado una *identificador*, que es lo que el código que se usa para hacer referencia a él.  
  
## <a name="rules"></a>Reglas  
 El nombre de un elemento en Visual Basic debe observar las reglas siguientes:  
  
-   Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).  
  
-   Solo debe contener caracteres alfabéticos, dígitos decimales y caracteres de subrayado.  
  
-   Debe contener al menos un carácter alfabético o dígito decimal si empieza con un carácter de subrayado.  
  
-   No debe superar los 1023 caracteres.  
  
 La longitud máxima de 1023 caracteres también se aplica a toda la cadena de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 El ejemplo siguiente muestra algunos nombres de elemento válido.  
  
 `aB123__45`  
  
 `_567`  
  
 El ejemplo siguiente muestra algunos nombres de elemento no válido. El primero contiene sólo un carácter de subrayado, la segunda comienza con un dígito decimal y el tercero contiene un carácter no válido ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Los nombres de elemento a partir de un carácter de subrayado (`_`) no forman parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que define los nombres de este tipo. Sin embargo, un carácter de subrayado en cualquier otra posición de un nombre de elemento es conforme a CLS.  
  
### <a name="name-length-guidelines"></a>Directrices de longitud de nombre  
 A efectos prácticos, su nombre debe ser lo más corta posible al identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce el tamaño de archivo de origen y de longitud de línea.  
  
 Por otro lado, el nombre no debe ser tan corto que no adecuadamente describe lo que representa el elemento y cómo lo utiliza el código. Esto es importante para la legibilidad del código. Si alguien más está intentando entenderla, o si usted está examinando mucho tiempo después de que lo escribió, nombres de elementos adecuados pueden guardar una cantidad considerable de tiempo.  
  
## <a name="escaped-names"></a>Nombres de escape  
 Por lo general, un nombre de elemento no debe coincidir con cualquiera de las palabras clave reservadas, como Visual Basic, `Case` o `Friend`. Sin embargo, puede definir un *nombre con escape*, que se encierra entre corchetes (`[ ]`). Un nombre con escape puede coincidir con cualquier palabra clave de Visual Basic, puesto que los corchetes quitar cualquier ambigüedad. También utiliza los corchetes cuando se hace referencia al nombre más adelante en el código.  
  
 En general, debe usar nombres de escape solo cuando:  
  
-   El código se migrado desde una versión anterior de Visual Basic que no reservó la palabra clave que se va a usar como un nombre; o  
  
-   Trabaja con código escrito en otro idioma en el que no se reserva la palabra clave dada.  
  
 De lo contrario, considere cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave. El entorno de desarrollo integrado (IDE) proporciona una manera fácil de hacerlo. Para obtener más información, consulte [refactorización](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Mayúsculas y minúsculas en nombres  
 Los nombres de elemento en Visual Basic distinguen entre mayúsculas y minúsculas. Esto significa que cuando el compilador compara dos nombres que difieran en mayúsculas o minúsculas, interpreta como el mismo nombre. Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.  
  
 Sin embargo, common language runtime (CLR) usa el enlace entre mayúsculas y minúsculas. Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas. Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`. Si posteriormente vuelve a compilar la clase y cambiar el nombre del elemento a `abc`, los demás ensamblados mediante la clase ya no pudieran acceder a ese elemento. Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.  
  
## <a name="names-and-locales"></a>Los nombres y las configuraciones regionales  
 Comparación de nombres es independiente de la configuración regional. Si dos nombres coinciden en una configuración regional, se garantiza que deben coincidir en todas las configuraciones regionales.  
  
## <a name="see-also"></a>Vea también

- [Elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)
