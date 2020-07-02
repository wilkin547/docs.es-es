---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620542"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>Ya no se puede establecer EnableViewStateMac en false

#### <a name="details"></a>Detalles

ASP.NET ya no permite a los desarrolladores especificar <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado. Solo afecta a las aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente en <code>false</code>.

#### <a name="suggestion"></a>Sugerencia

Se debe suponer que EnableViewStateMac se establece en true y se debe resolver cualquier error de MAC resultante (como se explica en [esta guía](https://support.microsoft.com/kb/2915218), que contiene varias resoluciones en función de la causa específica de los errores de MAC).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|
