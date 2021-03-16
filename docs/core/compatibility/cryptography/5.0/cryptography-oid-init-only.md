---
title: 'Cambio importante: Cryptography.Oid es funcionalmente de solo inicialización'
description: Obtenga información sobre el cambio importante en .NET 5 donde los establecedores de propiedad en la clase Cryptography.Oid ahora inician una excepción si intenta cambiar un valor.
ms.date: 08/16/2020
ms.openlocfilehash: aa1e72adcda61f2292574729e36cdc578bf907d2
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256873"
---
# <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>System.Security.Cryptography.Oid es funcionalmente de solo inicialización

La clase <xref:System.Security.Cryptography.Oid?displayProperty=fullName>, que se usa para representar valores de identificador de objeto ASN.1 y sus nombres "descriptivos", antes era completamente mutable. Esta mutabilidad se solía pasar por alto o aparecía por sorpresa. Los establecedores de propiedades ahora inician <xref:System.PlatformNotSupportedException> cuando se intenta cambiar el valor después de haberlo asignado.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores, los establecedores de propiedades en <xref:System.Security.Cryptography.Oid> se pueden usar para cambiar el valor de las propiedades <xref:System.Security.Cryptography.Oid.FriendlyName> y <xref:System.Security.Cryptography.Oid.Value>.

En .NET 5 y versiones posteriores, los establecedores de propiedad solo se pueden usar para inicializar el valor. Una vez que la propiedad tiene un valor, ya sea desde un constructor o una llamada anterior al establecedor de propiedades, dicho establecedor de propiedades siempre inicia <xref:System.PlatformNotSupportedException>.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio permite reutilizar objetos <xref:System.Security.Cryptography.Oid> como parte de los valores devueltos en las API públicas para reducir los perfiles de asignación de objetos. Evita la necesidad de crear copias "defensivas" temporales cuando se usan valores <xref:System.Security.Cryptography.Oid> como entradas.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Evite el uso de los establecedores de propiedades <xref:System.Security.Cryptography.Oid> que no sean para la inicialización de objetos. Para representar un nuevo valor, use una nueva instancia en lugar de cambiar el valor en un objeto existente.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

### Category

Cryptography

-->
