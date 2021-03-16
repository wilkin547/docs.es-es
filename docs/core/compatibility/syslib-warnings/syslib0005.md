---
title: Advertencia SYSLIB0005
description: Obtenga información sobre la obsolescencia que genera la advertencia en tiempo de compilación SYSLIB0005.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 9ed36d247d31bcebc499bd7ed3945490d9d901f9
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256378"
---
# <a name="syslib0005-the-global-assembly-cache-gac-is-not-supported"></a>SYSLIB0005: no se admite la caché global de ensamblados (GAC)

.NET Core y .NET 5 y versiones posteriores eliminan el concepto de caché global de ensamblados (GAC) presente en .NET Framework. Para ayudar a los desarrolladores a apartarse de estas API, algunas relacionadas con GAC se han marcado como obsoletas a partir de .NET 5.0. El uso de estas API genera una advertencia `SYSLIB0005` en tiempo de compilación.

Las siguientes API relacionadas con GAC se han marcado como obsoletas:

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

  Las bibliotecas y aplicaciones no deben usar la API <xref:System.Reflection.Assembly.GlobalAssemblyCache> para realizar determinaciones sobre el comportamiento en tiempo de ejecución, ya que siempre devuelve `false` en .NET Core y .NET 5+.

## <a name="workarounds"></a>Soluciones alternativas

Si la aplicación consulta a la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache>, considere la posibilidad de eliminar la llamada. Si usa el valor <xref:System.Reflection.Assembly.GlobalAssemblyCache> para elegir entre un flujo de "ensamblado en GAC" frente a un flujo de "ensamblado no en GAC" en tiempo de ejecución, vuelva a considerar si el flujo sigue teniendo sentido para una aplicación .NET 5+.

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Vea también

- [Caché global de ensamblados](../../../framework/app-domains/gac.md)
