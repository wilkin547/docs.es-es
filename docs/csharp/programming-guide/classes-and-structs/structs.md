---
title: 'Structs: Guía de programación de C#'
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 5150ff2d6edde0ac91bc6548fd499b76af614007
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705423"
---
# <a name="structs-c-programming-guide"></a>Structs (Guía de programación de C#)

Los structs se definen mediante la palabra clave [struct](../../language-reference/keywords/struct.md), por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
Los structs comparten la mayor parte de la sintaxis de las clases. El nombre de la estructura debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido. Los structs son más limitados que las clases en lo siguiente:  
  
- Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.  
- Un struct no puede declarar un constructor sin parámetros ni un finalizador.  
- Los structs se copian en la asignación. Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original. Es importante que lo recuerde al trabajar con colecciones de tipos de valor como `Dictionary<string, myStruct>`.  
- Los structs son tipos de valor, a diferencia de las clases, que son tipos de referencia.  
- A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.  
- Los structs pueden declarar constructores que tengan parámetros.
- Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Todos los structs heredan directamente de <xref:System.ValueType>, que hereda de <xref:System.Object>.  
- Un struct puede implementar interfaces.
- Una estructura no puede ser `null` y a una variable de estructura no se le puede asignar `null` a menos que la variable se declare como tipo de valor que admite un valor NULL.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](index.md)
- [Clases](classes.md)
- [Tipos de valores que aceptan valores NULL](../../language-reference/builtin-types/nullable-value-types.md)
- [Nombres de identificador](../inside-a-program/identifier-names.md)
- [Utilizar estructuras](using-structs.md)
- [Procedimiento para saber las diferencias entre pasar a un método un struct y una referencia a clase](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
