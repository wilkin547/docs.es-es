---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496679"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task ya no inicia una excepción ObjectDisposedException después de desechar un objeto

#### <a name="details"></a>Detalles

A excepción de <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, los métodos <xref:System.Threading.Tasks.Task?displayProperty=fullName> ya no inician una excepción <xref:System.ObjectDisposedException?displayProperty=fullName> después de desechar el objeto. Este cambio admite el uso de tareas en caché. Por ejemplo, un método puede devolver una tarea almacenada en caché para representar una operación completada en lugar de asignar una nueva tarea. Esto no era posible en versiones anteriores de .NET Framework, ya que cualquier consumidor de la tarea podía desecharla, lo que hacía que se volviera inutilizable.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que es posible que los métodos Task ya no inicien excepciones <xref:System.ObjectDisposedException?displayProperty=fullName> cuando el objeto se desecha. Si una aplicación dependía de esta excepción para conocer que se desechó una tarea, se debería actualizar para comprobar de forma explícita el estado de la tarea mediante <xref:System.Threading.Tasks.Task.Status>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
