---
title: Reglas de portabilidad y de interoperabilidad (análisis de código)
description: Más información sobre la portabilidad de reglas de análisis de código y las reglas de interoperabilidad
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.Portablityrules
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis rules, interoperability rules, portability rules
- portability rules
- warnings, portability
- interoperability rules
- warnings, interoperability
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a20cd77e13c4a8b95633d129990667f0a8de3ee8
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592409"
---
# <a name="portability-and-interoperability-rules"></a>Reglas de portabilidad e interoperabilidad

Las reglas de portabilidad admiten la portabilidad en diferentes plataformas. Las reglas de interoperabilidad admiten la interacción con clientes COM.

## <a name="in-this-section"></a>En esta sección

| Regla | Descripción |
| - | - |
| [CA1401: P/Invoke no debe estar visible](ca1401.md) | Un método público o protegido en un tipo público tiene el System.Runtime.InteropServices.Dllatributo ImportAttribute (también se implementa mediante la palabra clave declare en Visual Basic). No se deberían exponer estos métodos. |
| [CA1416: Validación de la compatibilidad con las plataformas](ca1416.md) | El uso de API dependientes de la plataforma en un componente hace que el código deje de funcionar en todas las plataformas. |
| [CA1417: no se usa `OutAttribute` en parámetros de cadena para P/Invoke](ca1417.md) | Los parámetros de cadena pasados por valor con el `OutAttribute` pueden desestabilizar el tiempo de ejecución si la cadena es una cadena interna. |
