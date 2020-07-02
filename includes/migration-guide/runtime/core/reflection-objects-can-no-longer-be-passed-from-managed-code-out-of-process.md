---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621434"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Los objetos Reflection ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso

#### <a name="details"></a>Detalles

Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Afecta a los siguientes tipos:<ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><xref:System.Reflection.MemberInfo?displayProperty=fullName> (y sus tipos derivados, incluidos <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> y <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</li></ul>Las llamadas a <code>IMarshal</code> para el objeto devuelven <code>E_NOINTERFACE</code>.

#### <a name="suggestion"></a>Sugerencia

Actualice el código de serialización para que funcione con objetos distintos a Reflection.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
