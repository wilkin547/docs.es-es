---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234281"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Las ventanas de WPF se representan sin recortes al ampliarse fuera de un monitor

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6 ejecutado en Windows 8 y versiones posteriores, se representa toda la ventana sin recortes cuando se amplía más allá de una única pantalla en un escenario de varios monitores. Esto es diferente de las versiones anteriores de .NET Framework, en las que se recortaban las ventanas de WPF que se ampliaban más allá de una pantalla.|
|Sugerencia|Este comportamiento (si hay que recortar o no) se puede establecer de manera explícita mediante el elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> de <code>&lt;appSettings&gt;</code> en el archivo de configuración de la aplicación, o bien estableciendo la propiedad <code>EnableMultiMonitorDisplayClipping</code> al inicio de la aplicación.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
