---
title: Llamar a una función DLL
description: Revise los problemas relacionados con la llamada a una función DLL que puede parecer confusa. El proceso de llamada de función difiere en función de si el tipo de valor devuelto se puede transferir en bloque de bits.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 90f8f47148e652a9942a35be1564bed94c155216
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620903"
---
# <a name="calling-a-dll-function"></a>Llamar a una función DLL
Aunque llamar a funciones DLL no administradas es prácticamente idéntico a llamar a otro código administrado, hay diferencias que pueden hacer que las funciones DLL parezcan confusas al principio. En esta sección se presentan temas que describen algunos de los problemas inusuales relacionados con las llamadas.  
  
 Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos de datos que tengan la misma representación en código administrado y no administrado. Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión (vea [Tipos que pueden o que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md)). Para llamar a una función que tiene una estructura que no puede transferirse en bloque de bits como su tipo de valor devuelto, se puede definir un tipo del asistente que pueda transferirse en bloque de bits del mismo tamaño que el tipo que no puede transferirse en bloque de bits y convertir los datos después de que la función devuelva un resultado.  
  
## <a name="in-this-section"></a>En esta sección  
 [Pasar estructuras](passing-structures.md)  
 Identifica los problemas de pasar estructuras de datos con un diseño predefinido.  
  
 [Funciones de devolución de llamada](callback-functions.md)  
 Proporciona información básica sobre las funciones de devolución de llamada.  
  
 [Cómo: Implementar funciones de devolución de llamada](how-to-implement-callback-functions.md)  
 Describe cómo implementar funciones de devolución de llamada en código administrado.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Consumir funciones DLL no administradas](consuming-unmanaged-dll-functions.md)  
 Se describe cómo llamar a funciones DLL no administradas mediante la invocación de plataforma.  
  
 [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md)  
 Describe cómo se declaran parámetros de método y se pasan argumentos a funciones exportadas por bibliotecas no administradas.
