---
title: Utilizar el doble búfer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777161"
---
# <a name="using-double-buffering"></a><span data-ttu-id="75e7d-102">Utilizar el doble búfer</span><span class="sxs-lookup"><span data-stu-id="75e7d-102">Using Double Buffering</span></span>
<span data-ttu-id="75e7d-103">Puede usar gráficos de doble búfer para reducir el parpadeo en las aplicaciones que contienen operaciones de pintura complejas.</span><span class="sxs-lookup"><span data-stu-id="75e7d-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="75e7d-104">.NET Framework contiene compatibilidad integrada para el búfer doble o puede administrar y representar manualmente gráficos.</span><span class="sxs-lookup"><span data-stu-id="75e7d-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75e7d-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="75e7d-105">In This Section</span></span>  
 [<span data-ttu-id="75e7d-106">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="75e7d-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="75e7d-107">Presenta compatibilidad de con .NET Framework concepto y esquemas de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="75e7d-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="75e7d-108">Cómo: Reducir el parpadeo de gráficos con un búfer doble en formularios y controles</span><span class="sxs-lookup"><span data-stu-id="75e7d-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="75e7d-109">Muestra cómo usar el valor predeterminado en doble búfer de soporte técnico de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75e7d-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="75e7d-110">Cómo: Administrar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="75e7d-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="75e7d-111">Muestra cómo administrar el almacenamiento en búfer doble en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="75e7d-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="75e7d-112">Cómo: Representar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="75e7d-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="75e7d-113">Muestra cómo representar gráficos de doble búfer.</span><span class="sxs-lookup"><span data-stu-id="75e7d-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="75e7d-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="75e7d-114">Reference</span></span>  
 <span data-ttu-id="75e7d-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="75e7d-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="75e7d-116">Método de control que permite el almacenamiento en doble búfer.</span><span class="sxs-lookup"><span data-stu-id="75e7d-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="75e7d-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="75e7d-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="75e7d-118">Proporciona métodos para crear búferes de gráficos.</span><span class="sxs-lookup"><span data-stu-id="75e7d-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="75e7d-119">Proporciona acceso al contexto de gráficos almacenados en búfer para un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75e7d-119">Provides access to the buffered graphics context for a application domain.</span></span>
