---
title: Utilizar controles WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5ea92b24a2ca30c0ad137d83c8f521a952ad0c6b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658498"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Usar controles de WPF en Windows Forms aplicaciones

Puede usar controles de Windows Presentation Foundation (WPF) en aplicaciones basadas en Windows Forms. Aunque se trata de dos tecnologías de vista diferentes, interoperan sin problemas.

El Diseñador de Windows Forms en Visual Studio proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation. Un control de WPF se hospeda en un control de Windows Forms especial denominado <xref:System.Windows.Forms.Integration.ElementHost>. Este control permite al control de WPF participar en el diseño del formulario y recibir mensajes de teclado y de mouse. En tiempo de diseño, puede organizar el <xref:System.Windows.Forms.Integration.ElementHost> control tal como lo haría con cualquier control de Windows Forms.

También puede usar controles Windows Forms en aplicaciones basadas en WPF. Para obtener más información, vea [diseñar XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Vea también

- [Interoperabilidad de WPF y Windows Forms](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
