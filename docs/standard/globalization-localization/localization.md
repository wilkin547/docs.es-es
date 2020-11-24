---
title: Localización
ms.date: 03/30/2017
helpviewer_keywords:
- culture, localization
- application development [.NET], localization
- globalization [.NET], localization
- code blocks
- international applications [.NET], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 5d47d002c714ea80b6f94c810f2dca726c273134
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829835"
---
# <a name="localization"></a>Localización

La localización es el proceso de traducción de los recursos de una aplicación en versiones localizadas para cada referencia cultural que la aplicación admite. Debe continuar con el paso de localización solo después de completar el paso de [revisión de localización](localizability-review.md) para verificar que la aplicación globalizada está lista para su localización.

Una aplicación que está lista para la localización se divide en dos bloques conceptuales: un bloque que contiene todos los elementos de la interfaz de usuario y otro que contiene código ejecutable. El bloque de la interfaz de usuario contiene solo los elementos localizables de dicha interfaz, como cadenas, mensajes de error, cuadros de diálogo, menús, recursos de objetos incrustados, etc., para la referencia cultural neutra. El bloque de código contiene solo el código de la aplicación que usarán todas las referencias culturales admitidas. Common Language Runtime admite un modelo de recursos de ensamblado satélite que separa el código ejecutable de una aplicación de sus recursos. Para obtener más información sobre la implementación de este modelo, vea [Recursos de .NET](../../framework/resources/index.md).

Para cada versión localizada de la aplicación, agregue un nuevo ensamblado satélite que contenga el bloque de la interfaz de usuario localizada traducida en el idioma apropiado para la referencia cultural de destino. El bloque de código de todas las referencias culturales debe permanecer igual. La combinación de una versión localizada del bloque de interfaz de usuario con el bloque de código produce una versión localizada de la aplicación.

El Kit de desarrollo de software (SDK) de Windows proporciona el Editor de recursos de Windows Forms (Winres.exe), que permite localizar rápidamente formularios Windows Forms para referencias culturales de destino. Para obtener información sobre el uso de esta herramienta, vea [Winres.exe (Editor de recursos de Windows Forms)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).

## <a name="see-also"></a>Vea también

- [Globalización y localización](index.md)
- [Revisión de localizabilidad](localizability-review.md)
- [Globalización](globalization.md)
- [Recursos de aplicaciones de escritorio](../../framework/resources/index.md)
