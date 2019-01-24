---
title: Información general sobre las constantes (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 34f3dee4edba58375c5c84b579e39a8a29ebc1bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737694"
---
# <a name="constants-overview-visual-basic"></a>Información general sobre las constantes (Visual Basic)
Una constante es un nombre descriptivo que ocupa el lugar de un número o una cadena que no cambia. Las constantes almacenan valores que, como el nombre implica, siguen siendo los mismos a lo largo de la ejecución de una aplicación. En gran medida, puede mejorar la legibilidad del código y facilitar su mantenimiento mediante constantes. Usarlos en el código que contiene valores que se vuelven a aparecer o que depende de algunos números que son difíciles de recordar o no tienen ningún significado obvio.  
  
## <a name="how-to-create-and-use-constants"></a>Cómo crear y utilizar constantes  
 Visual Basic contiene un número de constantes predefinidas, que se utilizan principalmente para la impresión y visualización. También puede crear sus propias constantes con el `Const` instrucción, utilizando las mismas directrices que lo haría para crear un nombre de variable. Si `Option Strict` es `On`, debe declarar explícitamente el tipo de constante.  
  
 El ámbito de una constante, que es el conjunto de todo el código que puede hacer referencia sin calificar su nombre, es el mismo que el de una variable declarada en la misma ubicación. Para crear una constante que existe dentro del ámbito de un procedimiento determinado, declarar dentro de ese procedimiento. Para crear una constante que está disponible en toda una aplicación, declare mediante el `Public` palabra clave en la sección de declaraciones de la clase.  
  
> [!NOTE]
>  Aunque las constantes algo son similares a las variables, no puede modificarlos o asignarles nuevos valores como a variables.  
  
 Las constantes utilizan en el código pueden definirse mediante el modelo de objetos para los controles o componentes que funciona con, o pueden ser definidas por el usuario (es decir, aquellos crea usted mismo).  
  
## <a name="compile-time-and-run-time-constants"></a>Constantes de tiempo de compilación y tiempo de ejecución  
 Una constante de tiempo de compilación se calcula en el momento en que se compila el código, mientras que solo se puede calcular una constante de tiempo de ejecución mientras se ejecuta la aplicación. Una constante de tiempo de compilación tendrá el mismo valor cada vez que se ejecuta una aplicación, mientras que una constante de tiempo de ejecución puede cambiar cada vez. Constantes de tiempo de compilación son necesarias para los casos, como los límites de matriz, las expresiones case o inicializadores de enumerador.  
  
## <a name="in-this-section"></a>En esta sección  
  
|de esquema JSON|Término|  
|---|---|  
|[Cómo: Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Explica cómo utilizar el `Const` instrucción para declarar una constante y establecer su valor; al declarar una constante, asigne un nombre descriptivo para el valor.|  
|[Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Describe cómo crear sus propias constantes, incluida la información sobre el ámbito y cómo evitar referencias circulares.|  
|[Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Proporciona información sobre cómo el compilador de Visual Basic inicializa las constantes cuando `Option Explicit` está desactivado.|  
|[Cómo: Agrupar valores de constantes relacionadas](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Muestra cómo agrupar valores constantes que están relacionados.|  
  
## <a name="reference"></a>Referencia  
  
|de esquema JSON|Término|  
|---|---|  
|[Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Muestra las constantes predefinidas por Visual Basic.|  
|[Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)|Describe el `Const` instrucción y su uso.|  
|[Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Describe el `Option Strict` instrucción y su uso.|  
  
## <a name="see-also"></a>Vea también
- [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Cómo: Inicializar una Variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
