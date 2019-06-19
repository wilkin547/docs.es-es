---
title: Utilizar el doble búfer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169920"
---
# <a name="using-double-buffering"></a><span data-ttu-id="0d215-102">Utilizar el doble búfer</span><span class="sxs-lookup"><span data-stu-id="0d215-102">Using Double Buffering</span></span>
<span data-ttu-id="0d215-103">Puede usar gráficos de doble búfer para reducir el parpadeo en las aplicaciones que contienen operaciones de pintura complejas.</span><span class="sxs-lookup"><span data-stu-id="0d215-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="0d215-104">.NET Framework contiene compatibilidad integrada para el búfer doble o puede administrar y representar manualmente gráficos.</span><span class="sxs-lookup"><span data-stu-id="0d215-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d215-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0d215-105">In This Section</span></span>  
 [<span data-ttu-id="0d215-106">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="0d215-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="0d215-107">Presenta compatibilidad de con .NET Framework concepto y esquemas de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="0d215-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="0d215-108">Cómo: Reducir el parpadeo de gráficos con un búfer doble en formularios y controles</span><span class="sxs-lookup"><span data-stu-id="0d215-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="0d215-109">Muestra cómo usar el valor predeterminado en doble búfer de soporte técnico de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d215-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="0d215-110">Cómo: Administrar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="0d215-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="0d215-111">Muestra cómo administrar el almacenamiento en búfer doble en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0d215-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="0d215-112">Cómo: Representar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="0d215-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="0d215-113">Muestra cómo representar gráficos de doble búfer.</span><span class="sxs-lookup"><span data-stu-id="0d215-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0d215-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="0d215-114">Reference</span></span>  
 <span data-ttu-id="0d215-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Método de control que permite el almacenamiento en doble búfer.</span><span class="sxs-lookup"><span data-stu-id="0d215-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="0d215-116"><xref:System.Drawing.BufferedGraphicsContext> Proporciona métodos para crear búferes de gráficos.</span><span class="sxs-lookup"><span data-stu-id="0d215-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="0d215-117">Proporciona acceso al contexto de gráficos almacenados en búfer para un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d215-117">Provides access to the buffered graphics context for a application domain.</span></span>
