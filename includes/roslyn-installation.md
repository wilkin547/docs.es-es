---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "72526776"
---
## <a name="installation-instructions---visual-studio-installer"></a>Instrucciones de instalación: Instalador de Visual Studio

Hay dos maneras distintas de buscar el **SDK de .NET Compiler Platform** en el **Instalador de Visual Studio**:

### <a name="install-using-the-visual-studio-installer---workloads-view"></a>Instalación con el Instalador de Visual Studio: visualización de cargas de trabajo

El SDK de .NET Compiler Platform no se selecciona automáticamente como parte de la carga de trabajo de desarrollo de extensiones de Visual Studio. Se debe seleccionar como un componente opcional.

1. Ejecute el **Instalador de Visual Studio**.
1. Haga clic en **Modificar**.
1. Active la carga de trabajo **Desarrollo de extensiones de Visual Studio**.
1. Abra el nodo **Desarrollo de extensiones de Visual Studio** en el árbol de resumen.
1. Active la casilla **SDK de .NET Compiler Platform**. La encontrará en última posición bajo los componentes opcionales.

Opcionalmente, también le interesará que el **Editor de DGML** muestre los gráficos en el visualizador:

1. Abra el nodo **Componentes individuales** en el árbol de resumen.
1. Active la casilla **Editor de DGML**.

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a>Instalación con el Instalador de Visual Studio: pestaña Componentes individuales

1. Ejecute el **Instalador de Visual Studio**.
1. Haga clic en **Modificar**.
1. Haga clic en la pestaña **Componentes individuales**.
1. Active la casilla **SDK de .NET Compiler Platform**. La encontrará en la parte superior bajo la sección **Compiladores, herramientas de compilación y tiempos de ejecución**.

Opcionalmente, también le interesará que el **Editor de DGML** muestre los gráficos en el visualizador:

1. Active la casilla **Editor de DGML**. La encontrará en la sección **Herramientas de código**.
