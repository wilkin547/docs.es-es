---
title: Declared Element Names
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
ms.openlocfilehash: cdba2b5f3e17fc6666ca653abd7f4bd7dfb31c4a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392927"
---
# <a name="declared-element-names-visual-basic"></a>Nombres de elementos declarados (Visual Basic)
Cada elemento declarado tiene un nombre, también denominado *identificador*, que es lo que el código utiliza para hacer referencia a él.  
  
## <a name="rules"></a>Reglas  
 Un nombre de elemento en Visual Basic debe respetar las siguientes reglas:  
  
- Debe empezar por un carácter alfabético o un carácter de subrayado ( `_` ).  
  
- Solo debe contener caracteres alfabéticos, dígitos decimales y caracteres de subrayado.  
  
- Debe contener al menos un carácter alfabético o un dígito decimal si comienza con un carácter de subrayado.  
  
- No debe tener más de 1023 caracteres de longitud.  
  
 El límite de longitud de 1023 caracteres también se aplica a toda la cadena de un nombre completo, como `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement` .  
  
 En el ejemplo siguiente se muestran algunos nombres de elemento válidos.  
  
 `aB123__45`  
  
 `_567`  
  
 En el ejemplo siguiente se muestran algunos nombres de elementos no válidos. La primera contiene solo un carácter de subrayado, la segunda comienza con un dígito decimal y la tercera contiene un carácter no válido ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> Los nombres de elemento que comienzan por un carácter de subrayado ( `_` ) no forman parte de la [independencia del lenguaje y de los componentes independientes del lenguaje](../../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede usar un componente que defina dichos nombres. Sin embargo, un carácter de subrayado en cualquier otra posición en un nombre de elemento es conforme a CLS.  
  
### <a name="name-length-guidelines"></a>Instrucciones de longitud de nombre  
 Como cuestión práctica, su nombre debe ser lo más corto posible y, al mismo tiempo, identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce la longitud de línea y el tamaño del archivo de origen.  
  
 Por otro lado, el nombre no debe ser tan corto que no describe adecuadamente lo que representa el elemento y cómo lo usa el código. Esto es importante para la legibilidad del código. Si alguien más está intentando comprenderlo, o si usted lo consulta mucho tiempo después de escribirlo, los nombres de elemento adecuados pueden ahorrar una cantidad considerable de tiempo.  
  
## <a name="escaped-names"></a>Nombres con escape  
 Por lo general, un nombre de elemento no debe coincidir con ninguna de las palabras clave reservadas por Visual Basic, como `Case` o `Friend` . Sin embargo, puede definir un *nombre con escape*, entre corchetes ( `[ ]` ). Un nombre con escape puede coincidir con cualquier palabra clave Visual Basic, ya que los corchetes quitan cualquier ambigüedad. También se usan los corchetes cuando se hace referencia al nombre más adelante en el código.  
  
 En general, los nombres de escape solo se deben usar cuando:  
  
- El código se migró desde una versión anterior de Visual Basic que no reservó la palabra clave que se usa como nombre. de  
  
- Está trabajando con código escrito en otro lenguaje en el que la palabra clave especificada no está reservada.  
  
 De lo contrario, debería considerar la posibilidad de cambiar el nombre del elemento si su nombre entra en conflicto con una palabra clave. El entorno de desarrollo integrado (IDE) proporciona una manera sencilla de hacerlo. Para obtener más información, consulte [refactorización](/visualstudio/ide/refactoring-in-visual-studio).  
  
## <a name="case-sensitivity-in-names"></a>Distinción de mayúsculas y minúsculas en nombres  
 Los nombres de elementos de Visual Basic no distinguen mayúsculas de minúsculas. Esto significa que cuando el compilador compara dos nombres que solo se diferencian en el uso de mayúsculas y minúsculas, los interpreta como el mismo nombre. Por ejemplo, considera que `ABC` y `abc` hacen referencia al mismo elemento declarado.  
  
 Sin embargo, Common Language Runtime (CLR) usa enlaces que distinguen entre mayúsculas y minúsculas. Por lo tanto, cuando genere un ensamblado o una DLL que pueda estar disponible para otros ensamblados, sus nombres ya no distinguirán entre mayúsculas o minúsculas. Por ejemplo, si define una clase que tiene un elemento denominado `ABC`, y otros ensamblados usan la clase mediante Common Language Runtime, deberán hacer referencia al elemento como `ABC`. Si posteriormente vuelve a compilar la clase y cambia el nombre del elemento a `abc` , los otros ensamblados que usen la clase ya no podrán tener acceso a ese elemento. Por lo tanto, cuando se lance una versión actualizada de un ensamblado, no se deben cambiar las mayúsculas o minúsculas de los elementos públicos.  
  
## <a name="names-and-locales"></a>Nombres y configuraciones regionales  
 La comparación de nombres es independiente de la configuración regional. Si dos nombres coinciden en una configuración regional, se garantiza que coincidan en todas las configuraciones regionales.  
  
## <a name="see-also"></a>Consulte también

- [Elementos declarados](index.md)
- [Características de los elementos declarados](declared-element-characteristics.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Instrucciones](../../../language-reference/statements/index.md)
