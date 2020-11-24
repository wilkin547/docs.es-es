---
title: Procedimiento para implementar e invocar un método de extensión personalizado - Guía de programación de C#
description: Aprenda a implementar métodos de extensión para cualquier tipo de .NET. El código de cliente puede usar los métodos mediante la incorporación de una referencia a un archivo DLL y la adición de una directiva using.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: d344489e88ddc2c8cac51afeb5bbc76bc7b42913
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099079"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Procedimiento para implementar e invocar un método de extensión personalizado (Guía de programación de C#)

En este tema se muestra cómo implementar sus propios métodos de extensión para cualquier tipo de .NET. El código de cliente puede usar los métodos de extensión agregando una referencia a la DLL que los contiene y agregando una directiva [using](../../language-reference/keywords/using-directive.md) que especifique el espacio de nombres en el que se definen los métodos de extensión.  
  
## <a name="to-define-and-call-the-extension-method"></a>Para definir y llamar al método de extensión  
  
1. Defina una [class](./static-classes-and-static-class-members.md) estática que contenga el método de extensión.  
  
     La clase debe estar visible para el código de cliente. Para obtener más información sobre las reglas de accesibilidad, vea [Modificadores de acceso](./access-modifiers.md).  
  
2. Implemente el método de extensión como un método estático con al menos la misma visibilidad que la clase contenedora.  
  
3. El primer parámetro del método especifica el tipo en el que opera el método; debe ir precedido del modificador [this](../../language-reference/keywords/this.md).  
  
4. En el código de llamada, agregue una directiva `using` para especificar el [espacio de nombres](../../language-reference/keywords/namespace.md) que contiene la clase del método de extensión.  
  
5. Llame a los métodos como si fueran métodos de instancia del tipo.  
  
     Tenga en cuenta que el primer parámetro no se especifica mediante el código de llamada, ya que representa el tipo al que se aplica el operador y el compilador ya conoce el tipo del objeto. Solo tiene que proporcionar argumentos para los parámetros comprendidos entre el 2 y `n`.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se implementa un método de extensión denominado `WordCount` en la clase `CustomExtensions.StringExtension`. El método opera en la clase <xref:System.String>, que se especifica como el primer parámetro de método. El espacio de nombres `CustomExtensions` se importa en el espacio de nombres de la aplicación y se llama al método dentro del método `Main`.  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a>Seguridad de .NET  

 Los métodos de extensión no presentan ninguna vulnerabilidad de seguridad específica. No se pueden usar nunca para suplantar los métodos existentes en un tipo, porque todos los conflictos de nombres se resuelven a favor de la instancia o del método estático definido por el tipo en cuestión. Los métodos de extensión no pueden tener acceso a los datos privados de la clase extendida.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Métodos de extensión](./extension-methods.md)
- [LINQ (Language Integrated Query)](../../linq/linq-in-csharp.md)
- [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md)
- [protected](../../language-reference/keywords/protected.md)
- [internal](../../language-reference/keywords/internal.md)
- [public](../../language-reference/keywords/public.md)
- [this](../../language-reference/keywords/this.md)
- [namespace](../../language-reference/keywords/namespace.md)
