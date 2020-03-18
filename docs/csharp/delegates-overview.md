---
title: Introducción a los delegados
description: Obtenga información sobre los delegados en este tema de introducción que presenta los conceptos básicos y explica los objetivos del diseño del lenguaje para los delegados.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 59b61d77-84e5-457b-8da5-fb5f24ca6ed6
ms.openlocfilehash: fd594f77c034533a1d5aee1d8279e9b727284311
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146234"
---
# <a name="introduction-to-delegates"></a>Introducción a los delegados

Los delegados proporcionan un mecanismo de *enlace en tiempo de ejecución* en .NET. Un enlace en tiempo de ejecución significa que se crea un algoritmo en el que el llamador también proporciona al menos un método que implementa parte del algoritmo.

Por ejemplo, considere la ordenación de una lista de estrellas en una aplicación de astronomía.
Puede decidir ordenar las estrellas por su distancia con respecto a la Tierra, por la magnitud de la estrella o por su brillo percibido.

En todos estos casos, el método Sort() hace básicamente lo mismo: organiza los elementos en la lista en función de una comparación. El código que compara dos estrellas es diferente para cada uno de los criterios de ordenación.

Este tipo de soluciones se ha usado en software durante aproximadamente medio siglo.
El concepto de delegado del lenguaje C# proporciona compatibilidad con el lenguaje de primera clase y seguridad de tipos en torno a este concepto.

Como verá más adelante en esta serie, el código de C# que escriba para algoritmos como este posee seguridad de tipos y aprovecha el lenguaje y el compilador para asegurarse de que los tipos coincidan con los argumentos y los tipos devueltos.

## <a name="language-design-goals-for-delegates"></a>Objetivos del diseño de lenguaje para los delegados

Los diseñadores de lenguaje enumeraron varios objetivos para la característica que se acabó convirtiendo en los delegados.

El equipo aspiraba a crear una construcción de lenguaje común que pudiera usarse para cualquier algoritmo de enlace en tiempo de ejecución. Esto permite a los desarrolladores aprender un concepto y usarlo en muchos problemas de software diferentes.

En segundo lugar, el equipo quería que se admitiesen llamadas a métodos únicos y multidifusión. Los delegados de multidifusión son delegados que encadenan varias llamadas a métodos.
Se verán ejemplos [más adelante en esta serie](delegate-class.md).

El equipo quería que los delegados admitiesen la misma seguridad de tipos que los desarrolladores esperan de todas las construcciones C#.

Por último, el equipo reconocía que un patrón de eventos es un patrón específico en el que los delegados, o cualquier algoritmo de enlace en tiempo de ejecución, resultan muy útiles. El equipo quería garantizar que el código de los delegados proporcionase una base para el patrón de eventos de .NET.

El resultado de todo ese trabajo fue la compatibilidad con los delegados y los eventos en C# y .NET. Los artículos restantes de esta sección tratarán sobre las características del lenguaje, la compatibilidad con bibliotecas y las expresiones comunes que se usan al trabajar con los delegados.

Obtendrá información sobre la palabra clave `delegate` y el código que genera. Conocerá las características de la clase `System.Delegate` y la manera en que se usan dichas características. Aprenderá a crear delegados con seguridad de tipos y métodos que se pueden invocar a través de delegados. También aprenderá a trabajar con delegados y eventos mediante expresiones lambda. Verá como los delegados se convierten en uno de los bloques de creación para LINQ. Descubrirá que los delegados son la base del patrón de eventos de .NET y entenderá en qué se diferencian.

En resumen, constatará que los delegados son una parte integral de la programación en .NET y de las operaciones con API de marco de trabajo.

Comencemos.

[Siguiente](delegate-class.md)
