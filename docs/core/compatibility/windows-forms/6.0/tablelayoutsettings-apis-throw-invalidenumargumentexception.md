---
title: 'Cambio importante: Algunas propiedades de TableLayoutSettings producen una excepción InvalidEnumArgumentException.'
description: Obtenga información sobre el cambio importante de .NET 6 que provoca que algunas API de TableLayoutSettings produzcan una excepción InvalidEnumArgumentException para argumentos no válidos.
ms.date: 01/18/2021
ms.openlocfilehash: 2da097122b935ec3a60c2bb009cc8ebbcff6468e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255729"
---
# <a name="selected-tablelayoutsettings-properties-throw-invalidenumargumentexception"></a>Ciertas propiedades de TableLayoutSettings producen la excepción InvalidEnumArgumentException

Ciertas propiedades de<xref:System.Windows.Forms.TableLayoutSettings> ahora producen una excepción <xref:System.ComponentModel.InvalidEnumArgumentException> si intenta asignar un valor incorrecto.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, estas propiedades producían una excepción <xref:System.ArgumentOutOfRangeException> si intentaba asignar un valor incorrecto. A partir de .NET 6, estas propiedades producen una excepción <xref:System.ComponentModel.InvalidEnumArgumentException> en estos casos.

## <a name="reason-for-change"></a>Motivo del cambio

La producción de la excepción <xref:System.ComponentModel.InvalidEnumArgumentException> es un funcionamiento acorde con la API de Windows Forms existente en situaciones similares. Esto también proporciona a los desarrolladores una mejor experiencia de depuración.

## <a name="version-introduced"></a>Versión introducida

.NET 6.0

## <a name="recommended-action"></a>Acción recomendada

- Actualice el código para evitar que se asignen valores incorrectos.
- Si es necesario, controle una excepción <xref:System.ComponentModel.InvalidEnumArgumentException> al obtener acceso a estas API.

## <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran las propiedades afectadas:

| Propiedad | Versión de la modificación |
|-|-|-|-|
| <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle?displayProperty=fullName> | Versión preliminar 1 |
| <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle?displayProperty=fullName> | Versión preliminar 1 |

<!--

### Affected APIs

- `P:System.Windows.Forms.TableLayoutPanel.CellBorderStyle`
- `P:System.Windows.Forms.TableLayoutPanel.GrowStyle`

### Category

Windows Forms

-->
