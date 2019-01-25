---
title: Período de duración en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
ms.openlocfilehash: 4c52d426fe5194a6eb61b232b8f17669b4477f16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667393"
---
# <a name="lifetime-in-visual-basic"></a>Período de duración en Visual Basic
El *duración* de un elemento declarado es el período de tiempo durante el cual está disponible para su uso. Las variables son los únicos elementos que tienen duración. Para este propósito, el compilador trata los parámetros de procedimiento y función que se devuelve como casos especiales de variables. La duración de una variable que representa el período de tiempo durante el cual puede contener un valor. Puede cambiar su valor a través de su duración, pero siempre contiene un valor.  
  
## <a name="different-lifetimes"></a>Diferentes períodos de duración  
 Un *variable miembro* (declarado en el nivel de módulo, fuera de cualquier procedimiento) normalmente tiene la misma duración que el elemento en el que se declara. Existe una variable no compartida declarada en una clase o estructura como una copia independiente para cada instancia de la clase o estructura en la que se ha declarado. Cada variable tiene la misma duración que su instancia. Sin embargo, un `Shared` variable tiene sólo una duración, que dura todo el tiempo que se está ejecutando la aplicación.  
  
 Un *variable local* (declarado dentro de un procedimiento) solo existe mientras se ejecuta el procedimiento en el que se declara. Esto también se aplica a los parámetros del procedimiento y a cualquier valor devuelto de función. Sin embargo, si ese procedimiento llama a otros procedimientos, las variables locales conservan sus valores mientras se ejecutan los procedimientos llamados.  
  
## <a name="beginning-of-lifetime"></a>A partir de duración  
 Duración de una variable local se inicia cuando el control entra en el procedimiento en el que se declara. Cada variable local se inicializa en el valor predeterminado de su tipo de datos tan pronto como el procedimiento inicia la ejecución. Cuando se encuentra el procedimiento una `Dim` instrucción que especifica los valores iniciales, Establece esas variables para esos valores, incluso si el código ya tenía asignado otros valores para ellos.  
  
 Cada miembro de una variable de estructura se inicializa como si fuese una variable independiente. De forma similar, cada elemento de una variable de matriz se inicializa individualmente.  
  
 Las variables declaradas dentro de un bloque dentro de un procedimiento (como un `For` bucle) se inicializan en la entrada al procedimiento. Estas inicializaciones surtan efecto si alguna vez ejecuta el código del bloque.  
  
## <a name="end-of-lifetime"></a>Final del período de duración  
 Cuando un procedimiento finaliza, no se conservan los valores de sus variables locales, y Visual Basic reclama su memoria. La próxima vez que se llame al procedimiento todas sus variables locales se crean desde cero y se reinicializa.  
  
 Cuando finaliza una instancia de una clase o estructura, sus variables no pierden su memoria y sus valores. Cada nueva instancia de la clase o estructura se crea y reinicializa variables no compartidas. Sin embargo, `Shared` variables se conservan hasta que la aplicación deja de ejecutarse.  
  
## <a name="extension-of-lifetime"></a>Extensión del período de duración  
 Si declara una variable local con el `Static` palabra clave, su duración es mayor que el tiempo de ejecución de su procedimiento. En la tabla siguiente se muestra cómo la declaración de procedimiento determina cuánto tiempo un `Static` variable existe.  
  
|Ubicación del procedimiento y el uso compartido|Comienza la duración de la variable estática|Extremos de la duración de la variable estática|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|En un módulo (compartido de forma predeterminada)|La primera vez que se llama al procedimiento|Cuando la aplicación deja de ejecutarse|  
|En una clase, `Shared` (el procedimiento no es un miembro de instancia)|La primera vez que se llama al procedimiento en una instancia específica o en el propio nombre de clase o estructura|Cuando la aplicación deja de ejecutarse|  
|En una instancia de una clase, no `Shared` (procedimiento es un miembro de instancia)|La primera vez que se llama al procedimiento en la instancia específica|Cuando se libera la instancia de la colección de elementos no utilizados (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Variables estáticas del mismo nombre  
 Puede declarar variables estáticas con el mismo nombre en más de un procedimiento. Si lo hace, el compilador de Visual Basic considera que cada variable es un elemento independiente. La inicialización de una de estas variables no afecta a los valores de los demás. Lo mismo se aplica si se define un procedimiento con un conjunto de sobrecargas y declara una variable estática con el mismo nombre en cada sobrecarga.  
  
## <a name="containing-elements-for-static-variables"></a>Que contiene los elementos de las Variables estáticas  
 Puede declarar una variable local estática dentro de una clase, es decir, dentro de un procedimiento de esa clase. Sin embargo, no puede declarar una variable local estática dentro de una estructura, como un miembro de estructura o como una variable local de un procedimiento dentro de esa estructura.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se declara una variable con el [estático](../../../../visual-basic/language-reference/modifiers/static.md) palabra clave. (Tenga en cuenta que no es necesario el `Dim` palabra clave cuando el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) usa un modificador, como `Static`.)  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>Comentarios  
 En el ejemplo anterior, la variable `applesSold` sigue existiendo después del procedimiento `runningTotal` devuelve al código de llamada. La próxima vez `runningTotal` se llama, `applesSold` mantiene su valor calculado anteriormente.  
  
 Si `applesSold` hubiera declarado sin usar `Static`, los valores acumulados anteriores no se conservará entre las llamadas a `runningTotal`. La próxima vez `runningTotal` llamó, `applesSold` habría sido vuelve a crear e inicializa en 0, y `runningTotal` habría devuelve simplemente el mismo valor con el que se llamó.  
  
### <a name="compiling-the-code"></a>Compilar el código  
 Puede inicializar el valor de una variable local estática como parte de su declaración. Si declara una matriz como `Static`, puede inicializar su rango (número de dimensiones), la longitud de cada dimensión y los valores de los elementos individuales.  
  
### <a name="security"></a>Seguridad  
 En el ejemplo anterior, puede generar la misma duración declarando `applesSold` en nivel de módulo. Si ha cambiado el ámbito de una variable de esta manera, sin embargo, el procedimiento ya no tendría acceso exclusivo a él. Dado que podrían tener acceso otros procedimientos `applesSold` y cambie su valor, el total acumulado podría ser poco confiable y el código podría ser más difícil de mantener.  
  
## <a name="see-also"></a>Vea también
- [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
