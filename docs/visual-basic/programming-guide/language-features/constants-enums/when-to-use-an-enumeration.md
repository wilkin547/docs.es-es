---
title: "Cuándo se debe usar una enumeración (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3b2937cc71c0c31bd8dce3d77fb33f48e1b5750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Cuándo se debe usar una enumeración (Visual Basic)
Las enumeraciones ofrecen una manera sencilla de trabajar con conjuntos de constantes relacionadas. Una enumeración, o `Enum`, es un nombre simbólico para un conjunto de valores. Las enumeraciones se tratan como tipos de datos y utilizarlas para crear conjuntos de constantes para su uso con las variables y propiedades.  
  
## <a name="when-to-use-an-enumeration"></a>Cuándo se debe utilizar una enumeración  
 Cada vez que un procedimiento acepta un conjunto limitado de variables, considere el uso de una enumeración. Las enumeraciones hacen código más legible y más claro, especialmente cuando se utilizan nombres significativos.  
  
 Las ventajas del uso de las enumeraciones incluyen:  
  
-   Reducir los errores producidos por números transpuestos o.  
  
-   Resulta muy sencillo cambiar valores en el futuro.  
  
-   Obtiene un código más fácil de leer, lo que significa que es menos probable que los errores se cuelen en los.  
  
-   Garantiza la compatibilidad con versiones posteriores. Con enumeraciones, el código es menos probable que produzca un error si en el futuro en que alguien cambia los valores correspondientes a los nombres de miembro.  
  
## <a name="naming-enumerations"></a>Enumeraciones de nomenclaturas  
 Utilice una convención de nomenclatura para los miembros de enumeración. Cuando [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] encuentra un nombre de miembro de una enumeración, se puede producir una excepción si otras bibliotecas de tipos que se hace referencia contienen el mismo nombre. Use un prefijo único que identifica los valores de la aplicación o componente.  
  
 Cuando se hace referencia a un miembro de una enumeración, debe calificar el nombre de miembro con el nombre de la enumeración o bien utilizar la `Imports` instrucción. Para obtener más información, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumeraciones predefinidas  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Proporciona una serie de enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResult`, para facilitar el código. Para obtener una lista de estos vea [constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Cómo: recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Enum (instrucción)](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
