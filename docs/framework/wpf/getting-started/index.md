---
title: "Introducción (WPF)"
ms.custom: 
ms.date: 01/26/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started [WPF]
- introduction [WPF]
- WPF [WPF], getting started
ms.assetid: 04f91da8-708c-46c7-8172-f1695ec847cd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eded6de5de269e7b49a87da31590267a5350f161
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2018
---
# <a name="getting-started-wpf"></a><span data-ttu-id="35938-102">Introducción (WPF)</span><span class="sxs-lookup"><span data-stu-id="35938-102">Getting Started (WPF)</span></span>
<span data-ttu-id="35938-103">Windows Presentation Foundation (WPF) es un marco de interfaz de usuario que crea aplicaciones de cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="35938-103">Windows Presentation Foundation (WPF) is a UI framework that creates desktop client applications.</span></span> <span data-ttu-id="35938-104">La plataforma de desarrollo de WPF admite un amplio conjunto de características de desarrollo de aplicaciones, incluido un modelo de aplicación, recursos, controles, gráficos, diseños, enlace de datos, documentos y seguridad.</span><span class="sxs-lookup"><span data-stu-id="35938-104">The WPF development platform supports a broad set of application development features, including an application model, resources, controls, graphics, layout, data binding, documents, and security.</span></span> <span data-ttu-id="35938-105">Es un subconjunto de .NET Framework, por lo que si ya ha creado aplicaciones con .NET Framework usando Windows Forms o ASP.NET, la experiencia de programación le resultará familiar.</span><span class="sxs-lookup"><span data-stu-id="35938-105">It is a subset of the .NET Framework, so if you have previously built applications with the .NET Framework using ASP.NET or Windows Forms, the programming experience should be familiar.</span></span> <span data-ttu-id="35938-106">WPF usa el lenguaje de marcado de aplicaciones extensible (XAML) para proporcionar un modelo declarativo para la programación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="35938-106">WPF uses the Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span> <span data-ttu-id="35938-107">Esta sección contiene temas que presentan WPF y le ayudarán a empezar a trabajar con él.</span><span class="sxs-lookup"><span data-stu-id="35938-107">This section has topics that introduce and help you get started with WPF.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="35938-108">¿Por dónde empiezo?</span><span class="sxs-lookup"><span data-stu-id="35938-108">Where Should I Start?</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35938-109">Deseo comenzar de inmediato…</span><span class="sxs-lookup"><span data-stu-id="35938-109">I want to jump right in…</span></span>|[<span data-ttu-id="35938-110">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="35938-110">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|  
|<span data-ttu-id="35938-111">¿Cómo puedo diseñar la interfaz de usuario de la aplicación?</span><span class="sxs-lookup"><span data-stu-id="35938-111">How do I design the application UI?</span></span>|[<span data-ttu-id="35938-112">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35938-112">Designing XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)|  
|<span data-ttu-id="35938-113">Novedades de .NET</span><span class="sxs-lookup"><span data-stu-id="35938-113">New to .NET?</span></span>|<span data-ttu-id="35938-114">[Información general acerca de .NET Framework](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="35938-114">[Overview of the .NET Framework](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span></span><br /><br /> <span data-ttu-id="35938-115">[.NET Framework Application Essentials](../../../../docs/standard/application-essentials.md) (Elementos esenciales de aplicaciones .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="35938-115">[.NET Framework Application Essentials](../../../../docs/standard/application-essentials.md)</span></span><br /><br /> <span data-ttu-id="35938-116">[Introducción a Visual C# y Visual Basic](https://msdn.microsoft.com/library/dd492171\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="35938-116">[Getting Started with Visual C# and Visual Basic](https://msdn.microsoft.com/library/dd492171\(v=vs.140\).aspx)</span></span>|  
|<span data-ttu-id="35938-117">Más información sobre WPF...</span><span class="sxs-lookup"><span data-stu-id="35938-117">Tell me more about WPF…</span></span>|[<span data-ttu-id="35938-118">Introducción a WPF en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35938-118">Introduction to WPF in Visual Studio</span></span>](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)<br /><br /> [<span data-ttu-id="35938-119">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="35938-119">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)<br /><br /> [<span data-ttu-id="35938-120">Controles</span><span class="sxs-lookup"><span data-stu-id="35938-120">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)<br /><br /> [<span data-ttu-id="35938-121">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="35938-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)|  
|<span data-ttu-id="35938-122">¿Es un desarrollador de Windows Forms?</span><span class="sxs-lookup"><span data-stu-id="35938-122">Are you a Windows Forms developer?</span></span>|[<span data-ttu-id="35938-123">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="35938-123">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)<br /><br /> [<span data-ttu-id="35938-124">Interoperabilidad entre Windows Forms y WPF</span><span class="sxs-lookup"><span data-stu-id="35938-124">WPF and Windows Forms Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)|  
  
## <a name="see-also"></a><span data-ttu-id="35938-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="35938-125">See Also</span></span>  
 [<span data-ttu-id="35938-126">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="35938-126">Class Library</span></span>](../../../../docs/framework/wpf/class-library-wpf.md)  
 [<span data-ttu-id="35938-127">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="35938-127">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
 [<span data-ttu-id="35938-128">Centro para desarrolladores de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="35938-128">.NET Framework Developer Center</span></span>](https://www.microsoft.com/net)
