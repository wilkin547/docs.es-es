---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621446"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Las ventanas de WPF se representan sin recortes al ampliarse fuera de un monitor

#### <a name="details"></a>Detalles

En .NET Framework 4.6 ejecutado en Windows 8 y versiones posteriores, se representa toda la ventana sin recortes cuando se amplía más allá de una única pantalla en un escenario de varios monitores. Esto es diferente de las versiones anteriores de .NET Framework, en las que se recortaban las ventanas de WPF que se ampliaban más allá de una pantalla.

#### <a name="suggestion"></a>Sugerencia

Este comportamiento (si hay que recortar o no) se puede establecer de manera explícita mediante el elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> de <code>&lt;appSettings&gt;</code> en el archivo de configuración de la aplicación, o bien estableciendo la propiedad <code>EnableMultiMonitorDisplayClipping</code> al inicio de la aplicación.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
