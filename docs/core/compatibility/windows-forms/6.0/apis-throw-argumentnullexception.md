---
title: 'Cambio importante: Algunas API inician la excepción ArgumentNullException'
description: Obtenga información sobre el cambio importante en .NET 6 por el que algunas API validan argumentos y ahora inician una excepción ArgumentNullException.
ms.date: 01/29/2021
ms.openlocfilehash: ca7f32739237715657350f52d2523b0ce378364d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255742"
---
# <a name="some-apis-throw-argumentnullexception"></a>Algunas API inician la excepción ArgumentNullException

Algunas API ahora validan los parámetros de entrada e inician una excepción <xref:System.ArgumentNullException> donde anteriormente iniciaban una excepción <xref:System.NullReferenceException>, si se invocaban con argumentos de entrada `null`.

## <a name="change-description"></a>Descripción del cambio

En las versiones anteriores de .NET, las API afectadas iniciaban una excepción <xref:System.NullReferenceException> si la invocación se realizaba con un argumento que es `null`.

A partir de .NET 6, las API afectadas iniciaban una excepción <xref:System.ArgumentNullException> si la invocación se realizaba con un argumento que es `null`.

## <a name="reason-for-change"></a>Motivo del cambio

Iniciar <xref:System.ArgumentNullException> se ajusta al comportamiento del entorno de ejecución .NET. Proporciona una mejor experiencia de depuración al comunicar claramente qué argumento produjo la excepción.

## <a name="version-introduced"></a>Versión introducida

.NET 6.0

## <a name="recommended-action"></a>Acción recomendada

- Revise y, si es necesario, actualice el código para evitar pasar argumentos de entrada `null` a las API afectadas.
- Si el código controla <xref:System.NullReferenceException>, reemplace o agregue un controlador adicional para <xref:System.ArgumentNullException>.

## <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran las propiedades afectadas:

| Propiedad | Versión de la modificación |
|-|-|-|-|
| <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName> | Versión preliminar 1 |

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->
