---
title: Utilizar el doble búfer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 9b09210eba0ac3a141219a7cdbff15f22c6ed003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523915"
---
# <a name="using-double-buffering"></a><span data-ttu-id="3f838-102">Utilizar el doble búfer</span><span class="sxs-lookup"><span data-stu-id="3f838-102">Using Double Buffering</span></span>
<span data-ttu-id="3f838-103">Puede usar gráficos de doble búfer para reducir el parpadeo en las aplicaciones que contienen operaciones de dibujo complejas.</span><span class="sxs-lookup"><span data-stu-id="3f838-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="3f838-104">.NET Framework contiene compatibilidad integrada para almacenamiento en búfer doble o puede administrar y representar manualmente gráficos.</span><span class="sxs-lookup"><span data-stu-id="3f838-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f838-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3f838-105">In This Section</span></span>  
 [<span data-ttu-id="3f838-106">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="3f838-106">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="3f838-107">Introduce el soporte de con .NET Framework concepto y los contornos de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="3f838-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="3f838-108">Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles</span><span class="sxs-lookup"><span data-stu-id="3f838-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="3f838-109">Muestra cómo utilizar el valor predeterminado el doble búfer soporte técnico de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f838-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="3f838-110">Administrar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="3f838-110">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="3f838-111">Muestra cómo administrar el almacenamiento en búfer doble en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3f838-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="3f838-112">Representar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="3f838-112">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="3f838-113">Muestra cómo representar gráficos de doble búfer.</span><span class="sxs-lookup"><span data-stu-id="3f838-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3f838-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="3f838-114">Reference</span></span>  
 <span data-ttu-id="3f838-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="3f838-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="3f838-116">Método de control que permite el almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="3f838-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="3f838-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="3f838-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="3f838-118">Proporciona métodos para crear búferes de gráficos.</span><span class="sxs-lookup"><span data-stu-id="3f838-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="3f838-119">Proporciona acceso al contexto de gráficos almacenados en búfer para un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f838-119">Provides access to the buffered graphics context for a application domain.</span></span>
