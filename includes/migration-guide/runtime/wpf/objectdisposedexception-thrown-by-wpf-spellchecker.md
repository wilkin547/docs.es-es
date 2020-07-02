---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621834"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>El corrector ortográfico de WPF inicia la excepción ObjectDisposedException

#### <a name="details"></a>Detalles

En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=fullName>. Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa. Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.

#### <a name="suggestion"></a>Sugerencia

Actualizar a .NET Framework 4.7

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|
