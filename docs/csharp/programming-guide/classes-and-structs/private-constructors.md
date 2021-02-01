---
title: 'Constructores privados: Guía de programación de C#'
description: Un constructor privado es un constructor de instancia especial de C# que se usa para restringir el modo en el que se puede crear un objeto. Se puede usar con métodos de fábrica u otras expresiones de construcción.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 980a638fbe6250b3d47a3effc7cbad5ec57fbcad
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899410"
---
# <a name="private-constructors-c-programming-guide"></a>Constructores privados (Guía de programación de C#)

Un constructor privado es un constructor de instancia especial. Se usa generalmente en clases que contienen solo miembros estáticos. Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases (excepto las anidadas) no podrán crear instancias de esta clase. Por ejemplo:  
  
 [!code-csharp[ClassWithPrivateConstructorExample#1](snippets/private-constructors/Program.cs#1)]
  
 La declaración de un constructor vacío evita la generación automática de un constructor sin parámetros. Observe que si no usa un modificador de acceso en el constructor, este será privado de manera predeterminada. En cambio, normalmente se usa el modificador [private](../../language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.  
  
 Los constructores privados se usan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase. Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática. Para obtener más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Ejemplo  

 El siguiente es un ejemplo de clase que usa un constructor privado.  
  
 [!code-csharp[CounterClassWithPrivateConstructor#2](snippets/private-constructors/Program.cs#2)]
  
 Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:  
  
 [!code-csharp[ErrorInstantiatingUsingPrivateConstructor#13](snippets/private-constructors/Program.cs#3)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea la sección [Constructores privados](~/_csharplang/spec/classes.md#private-constructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Constructores](./constructors.md)
- [Finalizadores](./destructors.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)
