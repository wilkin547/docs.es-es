---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621407"
---
### <a name="wpf-printing-stack-update"></a>Actualización de la pila de impresión de WPF

#### <a name="details"></a>Detalles

Las API de impresión de WPF en las que se usa <xref:System.Printing.PrintQueue?displayProperty=fullName> ahora llaman a la API Print Document Package de Windows en lugar de la API XPS Print, que está en desuso. El cambio se realizó con la facilidad en mente; ni los usuarios ni los desarrolladores deberían percibir cambios en el comportamiento o el uso de la API. La nueva pila de impresión está habilitada de forma predeterminada cuando se ejecuta en Windows 10 Creators Update. La pila de impresión antigua seguirá funcionando como antes en las versiones anteriores de Windows.

#### <a name="suggestion"></a>Sugerencia

Para usar la pila antigua en Windows 10 Creators Update, establezca el valor <code>UseXpsOMPrinting</code> REG_DWORD de la clave del Registro <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> en <code>1</code>.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7|
|Tipo|Tiempo de ejecución|
