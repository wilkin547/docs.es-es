---
title: Utilizar controles WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460698"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="f0842-102">Usar controles de WPF en Windows Forms aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f0842-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="f0842-103">Puede usar controles de Windows Presentation Foundation (WPF) en aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f0842-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="f0842-104">Aunque se trata de dos tecnologías de vista diferentes, interoperan sin problemas.</span><span class="sxs-lookup"><span data-stu-id="f0842-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="f0842-105">El Diseñador de Windows Forms en Visual Studio proporciona un entorno de diseño visual para hospedar controles de Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="f0842-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="f0842-106">Un control de WPF se hospeda en un control de Windows Forms especial denominado <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="f0842-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="f0842-107">Este control permite al control de WPF participar en el diseño del formulario y recibir mensajes de teclado y de mouse.</span><span class="sxs-lookup"><span data-stu-id="f0842-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="f0842-108">En tiempo de diseño, puede organizar el control <xref:System.Windows.Forms.Integration.ElementHost> tal como lo haría con cualquier control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f0842-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="f0842-109">También puede usar controles Windows Forms en aplicaciones basadas en WPF.</span><span class="sxs-lookup"><span data-stu-id="f0842-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="f0842-110">Para obtener más información, vea [diseñar XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f0842-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0842-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0842-111">See also</span></span>

- [<span data-ttu-id="f0842-112">Interoperabilidad de WPF y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0842-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
