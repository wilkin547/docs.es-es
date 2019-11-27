---
title: Información general sobre las constantes
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 9ccddfe44757c76992d641094e21ec8c2110ef83
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338340"
---
# <a name="constants-overview-visual-basic"></a>Información general sobre las constantes (Visual Basic)
Una constante es un nombre significativo que ocupa el lugar de un número o una cadena que no cambia. Las constantes almacenan valores que, como el nombre implica, siguen siendo los mismos en la ejecución de una aplicación. Puede mejorar considerablemente la legibilidad del código y facilitar el mantenimiento mediante el uso de constantes. Úselos en el código que contiene valores que vuelven a aparecer o que dependen de ciertos números que son difíciles de recordar o no tienen ningún significado obvio.  
  
## <a name="how-to-create-and-use-constants"></a>Cómo crear y usar constantes  
 Visual Basic contiene varias constantes predefinidas, que se usan principalmente para imprimir y mostrar. También puede crear sus propias constantes con la instrucción `Const`, con las mismas instrucciones que para crear un nombre de variable. Si `Option Strict` es `On`, debe declarar explícitamente el tipo constante.  
  
 El ámbito de una constante, que es el conjunto de todo el código que puede hacer referencia a él sin calificar su nombre, es el mismo que el de una variable declarada en la misma ubicación. Para crear una constante que exista dentro del ámbito de un procedimiento determinado, declárela dentro de ese procedimiento. Para crear una constante que esté disponible en toda una aplicación, declárela mediante la palabra clave `Public` en la sección declaraciones de la clase.  
  
> [!NOTE]
> Aunque las constantes son parecidas a las variables, no se pueden modificar o asignarles nuevos valores como se puede hacer con las variables.  
  
 Las constantes que se usan en el código pueden definirse mediante el modelo de objetos para los controles o componentes con los que se trabaja, o bien pueden ser definidas por el usuario (es decir, las que se crean).  
  
## <a name="compile-time-and-run-time-constants"></a>Constantes en tiempo de compilación y en tiempo de ejecución  
 Una constante de tiempo de compilación se calcula en el momento en que se compila el código, mientras que una constante en tiempo de ejecución solo se puede calcular mientras la aplicación se está ejecutando. Una constante de tiempo de compilación tendrá el mismo valor cada vez que se ejecute una aplicación, mientras que una constante en tiempo de ejecución puede cambiar cada vez. Las constantes en tiempo de compilación son necesarias para los casos como límites de matriz, expresiones Case o inicializadores de enumerador.  
  
## <a name="in-this-section"></a>Esta sección  
  
|Definición|Término|  
|---|---|  
|[Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Explica cómo usar la instrucción `Const` para declarar una constante y establecer su valor; al declarar una constante, se asigna un nombre descriptivo al valor.|  
|[Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Describe cómo crear sus propias constantes, incluida información sobre el ámbito y cómo evitar referencias circulares.|  
|[Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Proporciona información sobre cómo el compilador de Visual Basic inicializa las constantes cuando se desactiva `Option Explicit`.|  
|[Agrupar valores de constantes relacionadas](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Muestra cómo agrupar los valores constantes relacionados.|  
  
## <a name="reference"></a>Referencia  
  
|Definición|Término|  
|---|---|  
|[Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Muestra las constantes predefinidas por Visual Basic.|  
|[Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)|Describe la instrucción `Const` y su uso.|  
|[Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Describe la instrucción `Option Strict` y su uso.|  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
