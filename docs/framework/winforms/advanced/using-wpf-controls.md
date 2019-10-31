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
ms.openlocfilehash: 5e05ec7fc503565333a4d05662a4e40d8d1193af
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197467"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Usar controles de WPF en Windows Forms aplicaciones

Puede usar controles de Windows Presentation Foundation (WPF) en aplicaciones basadas en Windows Forms. Aunque se trata de dos tecnologías de vista diferentes, interoperan sin problemas.

El Diseñador de Windows Forms en Visual Studio proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation. Un control de WPF se hospeda en un control de Windows Forms especial denominado <xref:System.Windows.Forms.Integration.ElementHost>. Este control permite al control de WPF participar en el diseño del formulario y recibir mensajes de teclado y de mouse. En tiempo de diseño, puede organizar el control <xref:System.Windows.Forms.Integration.ElementHost> tal como lo haría con cualquier control Windows Forms.

También puede usar controles Windows Forms en aplicaciones basadas en WPF. Para obtener más información, vea [diseñar XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Vea también

- [Interoperabilidad de WPF y Windows Forms](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
