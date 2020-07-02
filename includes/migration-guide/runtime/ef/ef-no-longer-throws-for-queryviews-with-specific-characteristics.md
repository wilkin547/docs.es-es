---
ms.openlocfilehash: c6c897c13c84ce4b2be21da18e5702365518f286
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620626"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF ya no inicia excepciones para elementos QueryView con características específicas

#### <a name="details"></a>Detalles

Entity Framework ya no inicia una excepción <xref:System.StackOverflowException?displayProperty=fullName> cuando una aplicación ejecuta una consulta que usa QueryView con una propiedad de navegación 0..1 que intenta incluir las entidades relacionadas como parte de la consulta. Por ejemplo, mediante una llamada a <code>.Include(e =&gt; e.RelatedNavProp)</code>.

#### <a name="suggestion"></a>Sugerencia

Este cambio solo afecta al código que usa QueryViews con relaciones 1-0..1 cuando se ejecutan consultas que realizan llamadas a .Include. Mejora la fiabilidad y debe ser transparente para casi todas las aplicaciones. Pero puede deshabilitarlo si causa un comportamiento inesperado; para ello, agregue la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|
