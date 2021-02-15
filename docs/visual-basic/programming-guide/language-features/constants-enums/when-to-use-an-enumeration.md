---
description: 'Más información acerca de: Cuándo usar una enumeración (Visual Basic)'
title: Cuándo se debe utilizar una enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: a29d0e3bb8ac99baf5d43827a8b58701eddcfbdd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480744"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Cuándo se debe usar una enumeración (Visual Basic)

Las enumeraciones ofrecen una manera sencilla de trabajar con conjuntos de constantes relacionadas. Una enumeración, o `Enum` , es un nombre simbólico para un conjunto de valores. Las enumeraciones se tratan como tipos de datos y se pueden usar para crear conjuntos de constantes que se usan con variables y propiedades.  
  
## <a name="when-to-use-an-enumeration"></a>Cuándo se debe utilizar una enumeración  

 Siempre que un procedimiento acepte un conjunto limitado de variables, considere la posibilidad de usar una enumeración. Las enumeraciones hacen que el código sea más claro y legible, especialmente cuando se usan nombres descriptivos.  
  
 Las ventajas de utilizar enumeraciones incluyen:  
  
- Reduce los errores causados por la transposición o la escritura indebida de números.  
  
- Facilita el cambio de valores en el futuro.  
  
- Facilita la lectura del código, lo que significa que es menos probable que se produzcan errores en él.  
  
- Garantiza la compatibilidad con versiones posteriores. Con las enumeraciones, es menos probable que se produzca un error en el código si en el futuro alguien cambia los valores correspondientes a los nombres de miembro.  
  
## <a name="naming-enumerations"></a>Enumeración de nomenclatura  

 Use una Convención de nomenclatura para los miembros de enumeración. Cuando Visual Basic encuentra un nombre de miembro de enumeración, se puede producir una excepción si otras bibliotecas de tipos a las que se hace referencia contienen el mismo nombre. Use un prefijo único que identifique los valores de la aplicación o componente.  
  
 Al hacer referencia a un miembro de una enumeración, debe calificar el nombre del miembro con el nombre de la enumeración, o bien usar la `Imports` instrucción. Para obtener más información, vea [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumeraciones predefinidas  

 Visual Basic proporciona varias enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResult` , para facilitar el código. Para obtener una lista de estos [, vea constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Consulte también

- [Cómo: Declarar una enumeración](how-to-declare-enumerations.md)
- [Procedimiento para hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Procedimiento para determinar la cadena asociada a un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Instrucción Enum](../../../language-reference/statements/enum-statement.md)
- [Constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md)
