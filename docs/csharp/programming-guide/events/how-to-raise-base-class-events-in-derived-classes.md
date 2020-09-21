---
title: 'Procedimiento Producir eventos de una clase base en clases derivadas: Guía de programación de C#'
description: Aprenda a generar eventos de una clase base en clases derivadas. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 5456639052310cc64854e32caa1df9b391c042cb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558027"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a>Procedimiento Producir eventos de una clase base en clases derivadas (Guía de programación de C#)
En el siguiente ejemplo sencillo se muestra la forma estándar de declarar eventos en una clase base para que también se puedan generar desde clases derivadas. Este patrón se usa mucho en las clases de Windows Forms de las bibliotecas de clases de .NET.  
  
 Al crear una clase que se pueda usar como clase base para otras clases, debe considerar el hecho de que los eventos son un tipo especial de delegado que solo se pueden invocar desde la clase que los haya declarado. Las clases derivadas no pueden invocar directamente a eventos declarados en la clase base. Aunque a veces pueda querer un evento que solo la clase base pueda generar, en la mayoría de los casos debería habilitar la clase derivada para invocar a eventos de clase base. Para ello, puede crear un método de invocación protegido en la clase base que encapsula el evento. Al llamar o invalidar a este método de invocación, las clases derivadas pueden invocar directamente al evento.  
  
> [!NOTE]
> No declare eventos virtuales en una clase base y los invalide en una clase derivada. El compilador de C# no los controla correctamente y no es posible decir si un suscriptor del evento derivado se está suscribiendo realmente al evento de clase base.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Eventos](./index.md)
- [Delegados](../delegates/index.md)
- [Modificadores de acceso](../classes-and-structs/access-modifiers.md)
- [Crear controladores de eventos en Windows Forms](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
