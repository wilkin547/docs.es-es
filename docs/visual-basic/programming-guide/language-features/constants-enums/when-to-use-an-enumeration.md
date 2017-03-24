---
title: "Cuándo utilizar una enumeración (Visual Basic) | Documentos de Microsoft"
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
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
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
ms.openlocfilehash: f22102a2e1e7eafd7fcf4db1f46af2cc622eba70
ms.lasthandoff: 03/13/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Cuándo se debe usar una enumeración (Visual Basic)
Las enumeraciones ofrecen una manera fácil de trabajar con conjuntos de constantes relacionadas. Una enumeración, o `Enum`, es un nombre simbólico para un conjunto de valores. Las enumeraciones se tratan como tipos de datos y se puede utilizar para crear conjuntos de constantes para su uso con variables y propiedades.  
  
## <a name="when-to-use-an-enumeration"></a>Cuándo se debe utilizar una enumeración  
 Cuando un procedimiento acepta un conjunto limitado de variables, considere la posibilidad de utilizar una enumeración. Las enumeraciones hacen código más claro y legible, especialmente cuando se utilizan nombres significativos.  
  
 Las ventajas de utilizar las enumeraciones incluyen:  
  
-   Reducir los errores producidos por números transpuestos o.  
  
-   Facilita cambiar los valores en el futuro.  
  
-   Hace el código más fácil de leer, lo que significa que es menos probable que los errores se cuelen en él.  
  
-   Garantiza la compatibilidad con versiones posteriores. Con enumeraciones, es menos probable que un error si en el futuro en que alguien cambia los valores correspondientes a los nombres de miembro el código.  
  
## <a name="naming-enumerations"></a>Nombres de enumeraciones  
 Utilice una convención de nomenclatura para los miembros de enumeración. Cuando [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] encuentra un nombre de miembro de una enumeración, se puede producir una excepción si otras bibliotecas de tipos que se hace referencia contienen el mismo nombre. Utilice un prefijo único que identifica los valores de la aplicación o componente.  
  
 Cuando se hace referencia a un miembro de una enumeración, debe calificar el nombre de miembro con el nombre de la enumeración o bien utilizar la `Imports` instrucción. Para obtener más información, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumeraciones predefinidas  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona una serie de enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResul`t para facilitar el código. Para obtener una lista de estos, consulte [constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Cómo: hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Cómo: recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cómo: determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Enum (instrucción)](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
