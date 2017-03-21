---
title: "Información general de constantes (Visual Basic) | Documentos de Microsoft"
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
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 8004045d233da0db017b26b350743ad9f8d61845
ms.lasthandoff: 03/13/2017

---
# <a name="constants-overview-visual-basic"></a>Información general sobre las constantes (Visual Basic)
Una constante es un nombre significativo que toma el lugar de un número o una cadena que no cambia. Las constantes almacenan valores que, como su nombre indica, permanecen iguales durante la ejecución de una aplicación. En gran medida puede mejorar la legibilidad del código y facilitar su mantenimiento mediante constantes. Usarlas en código que contiene valores que reaparecen o que dependen de ciertos números que son difíciles de recordar o significado no sea evidente.  
  
## <a name="how-to-create-and-use-constants"></a>Cómo crear y utilizar constantes  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]contiene un número de constantes predefinidas, que se utilizan principalmente para imprimir y mostrar. También puede crear sus propias constantes con la `Const` instrucción, utilizando las mismas directrices que en la creación de un nombre de variable. Si `Option Strict` es `On`, debe declarar explícitamente el tipo de constante.  
  
 El ámbito de una constante, que es el conjunto de código que puede hacer referencia sin calificar su nombre, es el mismo que el de una variable declarada en la misma ubicación. Para crear una constante que exista en el ámbito de un procedimiento concreto, declárela dentro de dicho procedimiento. Para crear una constante disponible en toda la aplicación, declárela con la `Public` palabra clave en la sección de declaraciones de la clase.  
  
> [!NOTE]
>  Aunque constantes algo son similares a las variables, no puede modificarlos o asignarles valores nuevos como a variables.  
  
 Las constantes que utilizar en el código pueden definirse mediante el modelo de objetos para los controles o componentes con los que trabaja o pueden ser definidas por el usuario (es decir, aquellos crea usted mismo).  
  
## <a name="compile-time-and-run-time-constants"></a>Constantes de tiempo de compilación y tiempo de ejecución  
 Una constante de tiempo de compilación se calcula en el momento en que se compila el código, mientras que sólo se puede calcular una constante de tiempo de ejecución mientras se ejecuta la aplicación. Una constante de tiempo de compilación tendrá el mismo valor cada vez que se ejecuta una aplicación, mientras que una constante de tiempo de ejecución puede cambiar cada vez. Constantes de tiempo de compilación se requieren para casos como límites de matriz, expresiones de caso o inicializadores de enumerador.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Definición|Término|  
|---|---|  
|[Declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Explica cómo utilizar el `Const` instrucción para declarar una constante y establecer su valor; al declarar una constante, asignar un nombre significativo al valor.|  
|[Constantes definidas por el usuario](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Describe cómo crear sus propias constantes, información sobre ámbito y cómo evitar referencias circulares.|  
|[Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Proporciona información sobre cómo el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador inicializa las constantes cuando `Option Explicit` está desactivado.|  
|[Agrupar valores de constantes relacionadas](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Muestra cómo agrupar los valores constantes que se relacionan.|  
  
## <a name="reference"></a>Referencia  
  
|Definición|Término|  
|---|---|  
|[Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Muestra las constantes predefinidas por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)|Describe el `Const` instrucción y su uso.|  
|[Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Describe el `Option Strict` instrucción y su uso.|  
  
## <a name="see-also"></a>Vea también  
 [Información general de las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Cómo: inicializar una Variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
