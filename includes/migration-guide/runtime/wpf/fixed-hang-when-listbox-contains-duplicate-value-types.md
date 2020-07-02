---
ms.openlocfilehash: 5d5423d18091545ad9d50325900f5a9a4fff6dd9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622114"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Se ha corregido un bloqueo cuando ListBox contiene tipos de valores duplicados

#### <a name="details"></a>Detalles

Se ha corregido un problema por el que un elemento de virtualización<xref:System.Windows.Controls.ItemsControl> dejaba de responder durante el desplazamiento cuando la colección de elementos contenía objetos de tipo de valor duplicados.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
