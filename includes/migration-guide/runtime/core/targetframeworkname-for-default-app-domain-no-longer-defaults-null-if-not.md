---
ms.openlocfilehash: f955e270f709ddf6eea2e44bbcf386e372b9f6e3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621425"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>TargetFrameworkName para el dominio de aplicación predeterminado ya no tiene un valor NULL como valor predeterminado si no se establece

#### <a name="details"></a>Detalles

<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> anteriormente tenía un valor NULL en el dominio de aplicación predeterminado, a menos que se estableciera de forma explícita. A partir de la versión 4.6, la propiedad <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> del dominio de aplicación predeterminado tendrá un valor predeterminado derivado del elemento TargetFrameworkAttribute (si hay alguno presente). Los dominios de aplicación no predeterminados continuarán heredando su propiedad <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> del dominio de aplicación predeterminado (que no tendrá un valor NULL como valor predeterminado en la versión 4.6) a menos que se invalide de forma explícita.

#### <a name="suggestion"></a>Sugerencia

El código debería actualizarse para no depender de que <xref:System.AppDomainSetup.TargetFrameworkName> establezca un valor nulo como valor predeterminado. Si es necesario que esta propiedad continúe evaluándose como un valor nulo, puede establecerse en dicho valor de forma explícita.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
