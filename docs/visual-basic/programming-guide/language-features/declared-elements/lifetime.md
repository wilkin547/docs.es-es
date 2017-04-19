---
title: "Duración en Visual Basic | Documentos de Microsoft"
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
- static variables, lifetime
- static variables, Visual Basic
- declared elements, lifetime
- Shared variable lifetime
- lifetime, declared elements
- lifetime, Visual Basic
- lifetime
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
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
ms.openlocfilehash: fa0cbdf4a8fe5e8fc41e4e4f373c79451fb7b75f
ms.lasthandoff: 03/13/2017

---
# <a name="lifetime-in-visual-basic"></a>Período de duración en Visual Basic
El *duración* de un elemento declarado es el período de tiempo durante el cual está disponible para su uso. Las variables son los únicos elementos que tienen una duración. Para este propósito, el compilador trata los parámetros de procedimiento y función devuelve como casos especiales de variables. La duración de una variable representa el período de tiempo durante el cual puede contener un valor. Su valor puede cambiar durante toda su duración, pero siempre contiene un valor.  
  
## <a name="different-lifetimes"></a>Períodos de duración diferentes  
 Un *variable miembro* (declarado en el nivel de módulo, fuera de cualquier procedimiento) normalmente tiene la misma duración que el elemento en el que se declara. Una variable no compartida declarada en una clase o estructura existe como una copia independiente para cada instancia de la clase o estructura en la que se declara. Cada variable tiene la misma duración que su instancia. Sin embargo, un `Shared` variable tiene sólo una duración, que dura todo el tiempo que se ejecuta la aplicación.  
  
 Un *variable local* (declarado dentro de un procedimiento) sólo existe mientras se ejecuta el procedimiento en el que se declara. Esto también se aplica a los parámetros del procedimiento y a cualquier valor devuelto de función. Sin embargo, si ese procedimiento llama a otros procedimientos, las variables locales conservan sus valores mientras se ejecutan los procedimientos llamados.  
  
## <a name="beginning-of-lifetime"></a>Comienzo del período de duración  
 Duración de la variable local se inicia cuando el control entra en el procedimiento en el que se declara. Cada variable local se inicializa en el valor predeterminado de su tipo de datos tan pronto como el procedimiento inicia la ejecución. Cuando el procedimiento encuentra una `Dim` instrucción que especifica valores iniciales, Establece esas variables a esos valores, incluso si su código ya haya asignado otros valores para ellos.  
  
 Cada miembro de una variable de estructura se inicializa como si fuera una variable independiente. De forma similar, cada elemento de una variable de matriz se inicializa de manera individual.  
  
 Las variables declaradas dentro de un bloque dentro de un procedimiento (como un `For` bucle) se inicializan en la entrada al procedimiento. Estas inicializaciones tienen efecto independientemente de que el código ejecuta el bloque o no.  
  
## <a name="end-of-lifetime"></a>Final del período de duración  
 Cuando un procedimiento finaliza, no se conservan los valores de sus variables locales, y [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] recupera su memoria. La próxima vez que se llama al procedimiento, todas sus variables locales se crearla de nuevo y se reinicializan.  
  
 Cuando finaliza una instancia de una clase o estructura, sus variables no compartidas pierden su memoria y sus valores. Cada nueva instancia de la clase o estructura crea y reinicializa sus variables no compartidas. Sin embargo, `Shared` variables se conservan hasta que la aplicación deja de ejecutarse.  
  
## <a name="extension-of-lifetime"></a>Extensión de duración  
 Si declara una variable local con el `Static` (palabra clave), su duración sea mayor que el tiempo de ejecución de su procedimiento. La tabla siguiente muestra cómo la declaración de procedimiento determina cuánto tiempo un `Static` variable existe.  
  
|Ubicación de procedimiento y uso compartido|Comienza la duración de la variable estática|Extremos de la duración de la variable estática|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|En un módulo (compartido de forma predeterminada)|La primera vez que se llama al procedimiento|Cuando la aplicación deja de ejecutarse|  
|En una clase, `Shared` (el procedimiento no es un miembro de instancia)|La primera vez que se llama al procedimiento en una instancia específica o en el nombre de clase o estructura|Cuando la aplicación deja de ejecutarse|  
|En una instancia de una clase, no `Shared` (el procedimiento es un miembro de instancia)|La primera vez que se llama al procedimiento en la instancia específica|Cuando la instancia se libera para la recopilación de elementos no utilizados (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Variables estáticas del mismo nombre  
 Puede declarar variables estáticas con el mismo nombre en más de un procedimiento. Si lo hace, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador considera que cada variable es un elemento separado. La inicialización de una de estas variables no afecta a los valores de las demás. Lo mismo se aplica si se define un procedimiento con un conjunto de sobrecargas y declare una variable estática con el mismo nombre en cada sobrecarga.  
  
## <a name="containing-elements-for-static-variables"></a>Elementos contenedores para Variables estáticas  
 Puede declarar una variable local estática dentro de una clase, es decir, dentro de un procedimiento de esa clase. Sin embargo, no puede declarar una variable local estática dentro de una estructura como miembros de una estructura o como una variable local de un procedimiento dentro de esa estructura.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se declara una variable con el [estático](../../../../visual-basic/language-reference/modifiers/static.md) (palabra clave). (Tenga en cuenta que no es necesario el `Dim` palabra clave cuando la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) utiliza un modificador como `Static`.)  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrKeywords&#13;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>Comentarios  
 En el ejemplo anterior, la variable `applesSold` sigue existiendo después del procedimiento `runningTotal` devuelve al código de llamada. La próxima vez `runningTotal` se llama, `applesSold` mantiene su valor calculado anteriormente.  
  
 Si `applesSold` hubiera declarado sin usar `Static`, los valores acumulados anteriores no se conservarían a través de llamadas a `runningTotal`. La próxima vez `runningTotal` se llamó, `applesSold` habría sido vuelve a inicializa en 0, y `runningTotal` simplemente se habría devuelto el mismo valor con el que se llamó.  
  
### <a name="compiling-the-code"></a>Compilar el código  
 Puede inicializar el valor de una variable local estática como parte de su declaración. Si declara una matriz como `Static`, puede inicializar su rango (número de dimensiones), la longitud de cada dimensión y los valores de los elementos individuales.  
  
### <a name="security"></a>Seguridad  
 En el ejemplo anterior, puede generar la misma duración si declara `applesSold` a nivel de módulo. Si cambia el ámbito de una variable de este modo, sin embargo, el procedimiento ya no tendría acceso exclusivo a él. Dado que podrían tener acceso otros procedimientos `applesSold` y cambiar su valor, el total acumulado no sería fiable y el código podría ser más difícil de mantener.  
  
## <a name="see-also"></a>Vea también  
 [Compartido](../../../../visual-basic/language-reference/modifiers/shared.md)   
 [Nada](../../../../visual-basic/language-reference/nothing.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)
