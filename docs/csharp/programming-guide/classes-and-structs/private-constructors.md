---
title: 'Constructores privados: Guía de programación de C#'
description: Un constructor privado es un constructor de instancia especial de C# que se usa para restringir el modo en el que se puede crear un objeto. Se puede usar con métodos de fábrica u otras expresiones de construcción.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: a6b86ccb870da0262bcbc516e176e00d17724f9f
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864064"
---
# <a name="private-constructors-c-programming-guide"></a>Constructores privados (Guía de programación de C#)
Un constructor privado es un constructor de instancia especial. Se usa generalmente en clases que contienen solo miembros estáticos. Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases (excepto las anidadas) no podrán crear instancias de esta clase. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 La declaración de un constructor vacío evita la generación automática de un constructor sin parámetros. Observe que si no usa un modificador de acceso en el constructor, este será privado de manera predeterminada. En cambio, normalmente se usa el modificador [private](../../language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.  
  
 Los constructores privados se usan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase. Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática. Para obtener más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente es un ejemplo de clase que usa un constructor privado.  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea la sección [Constructores privados](~/_csharplang/spec/classes.md#private-constructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Constructores](./constructors.md)
- [Finalizadores](./destructors.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)
