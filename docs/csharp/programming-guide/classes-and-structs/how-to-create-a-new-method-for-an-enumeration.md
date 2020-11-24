---
title: Procedimiento para crear un método nuevo para una enumeración - Guía de programación de C#
description: Obtenga información sobre cómo usar métodos de extensión para agregar funcionalidad a una enumeración en C#. En este ejemplo se muestra un método de extensión denominado Passing para una enumeración denominada Grades.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 862eb86a5b0cc6b95302260874222bbc09d98132
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099417"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Procedimiento para crear un método nuevo para una enumeración (Guía de programación de C#)

Puede usar métodos de extensión para agregar funcionalidad a un tipo de enumeración concreto.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, la enumeración `Grades` representa las posibles calificaciones con letras que un alumno puede recibir en una clase. Un método de extensión denominado `Passing` se agrega al tipo `Grades` para que cada instancia de ese tipo "sepa" ahora si representa una calificación de aprobado o no.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 Tenga en cuenta que la clase `Extensions` también contiene una variable estática que se actualiza dinámicamente y que el valor devuelto del método de extensión refleja el valor actual de esa variable. Esto demuestra que, en segundo plano, los métodos de extensión se invocan directamente en la clase estática en donde se definen.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Métodos de extensión](./extension-methods.md)
