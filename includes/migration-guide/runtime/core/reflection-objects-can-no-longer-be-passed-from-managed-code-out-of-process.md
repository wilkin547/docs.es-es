---
ms.openlocfilehash: 38c774417fc94fa080bf2b82c04d575e9068cdcb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234269"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Los objetos Reflection ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso

|   |   |
|---|---|
|Detalles|Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Afecta a los siguientes tipos:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (y sus tipos derivados, incluidos <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> y <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Las llamadas a <code>IMarshal</code> para el objeto devuelven <code>E_NOINTERFACE</code>.|
|Sugerencia|Actualice el código de serialización para que funcione con objetos distintos a Reflection.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
