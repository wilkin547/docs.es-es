---
title: 'Atributos de C#: Un paseo por el lenguaje C# | Microsoft Docs'
description: "Obtenga información sobre la programación declarativa usando atributos en C#"
keywords: . NET, csharp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 9e7ad62e85df83f181fa4aa8ea6da56b6f739f14
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

<a id="attributes" class="xliff"></a>

# Atributos

Los tipos, los miembros y otras entidades en un programa de C # admiten modificadores que controlan ciertos aspectos de su comportamiento. Por ejemplo, la accesibilidad de un método se controla mediante los modificadores `public`, `protected`, `internal` y `private`. C # generaliza esta funcionalidad de manera que los tipos de información declarativa definidos por el usuario se puedan adjuntar a las entidades del programa y recuperarse en tiempo de ejecución. Los programas especifican esta información declarativa adicional mediante la definición y el uso de ***atributos***.

En el ejemplo siguiente se declara un atributo `HelpAttribute` que se puede colocar en entidades de programa para proporcionar vínculos a la documentación asociada.

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

Todas las clases de atributos se derivan de la clase base @System.Attribute proporcionada por la biblioteca estándar. Los atributos se pueden aplicar proporcionando su nombre, junto con cualquier argumento, entre corchetes, justo antes de la declaración asociada. Si el nombre de un atributo termina en `Attribute`, esa parte del nombre se puede omitir cuando se hace referencia al atributo. Por ejemplo, el atributo `HelpAttribute` se puede usar de la manera siguiente.

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

En este ejemplo se adjunta un atributo `HelpAttribute` a la clase `Widget`. También se agrega otro atributo `HelpAttribute` al método `Display` en la clase. Los constructores públicos de una clase de atributos controlan la información que se debe proporcionar cuando el atributo se adjunta a una entidad de programa. Se puede proporcionar información adicional haciendo referencia a las propiedades públicas de lectura y escritura de la clase de atributos (como la referencia a la propiedad `Topic` usada anteriormente).

Cuando se solicita un atributo determinado mediante reflexión, se invoca al constructor de la clase de atributos con la información proporcionada en el origen del programa y se devuelve la instancia de atributo resultante. Si se proporciona información adicional mediante propiedades, dichas propiedades se establecen en los valores dados antes de devolver la instancia del atributo.

>[!div class="step-by-step"]
[Anterior](delegates.md)

