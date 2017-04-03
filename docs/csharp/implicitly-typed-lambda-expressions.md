---
title: "Expresiones lambda con tipo implícito"
description: "Expresiones lambda con tipo implícito"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c3621f6feb29929d3681b6ed66cc12c5d8018ba1
ms.lasthandoff: 03/13/2017

---

# <a name="implicitly-typed-lambda-expressions"></a>Expresiones lambda con tipo implícito

No estoy usando `var` para declarar este árbol de expresión. No puede usar una declaración de variable con tipo implícito para declarar una expresión lambda.
Crea un problema de lógica circular para el compilador. La declaración `var` indica al compilador que detecte el tipo de variable del tipo de expresión en el lado derecho del operador de asignación. Una expresión lambda no tiene un tipo de tiempo de compilación, pero puede convertirse en cualquier tipo de expresión o delegado coincidente. Cuando asigna una expresión lambda a una variable de un tipo de expresión o delegado, indica al compilador que pruebe y convierta la expresión lambda en una expresión o delegado que coincida con la firma de la variable "assigned to". El compilador debe intentar que lo que se encuentra en el lado derecho de la asignación coincida con el tipo del lado izquierdo de la asignación. 

Ambos lados de la asignación no pueden indicar al compilador que se dirija al objeto del otro lado del operador de asignación y vea si coincide con el tipo.

Puede obtener más información sobre por qué el lenguaje de C# especifica ese comportamiento con la lectura de [este artículo](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (descarga de PDF).



