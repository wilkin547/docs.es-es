---
ms.openlocfilehash: dab6b435a885d862d08f94dd31de79625f19bcc0
ms.sourcegitcommit: 6472349821dbe202d01182bc2cfe9d7176eaaa6c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2019
ms.locfileid: "67870505"
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
