---
title: Utilizar contenedores de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: 8755a95434d3fed06a55cfca0f71d86e5521cb39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525026"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="802a5-102">Utilizar contenedores de gráficos</span><span class="sxs-lookup"><span data-stu-id="802a5-102">Using Graphics Containers</span></span>
<span data-ttu-id="802a5-103">A <xref:System.Drawing.Graphics> objeto proporciona métodos como <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, y <xref:System.Drawing.Graphics.DrawString%2A> para mostrar imágenes vectoriales, imágenes de trama y texto.</span><span class="sxs-lookup"><span data-stu-id="802a5-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="802a5-104">Un <xref:System.Drawing.Graphics> objeto también tiene varias propiedades que influyen en la calidad y la orientación de los elementos que se dibujan.</span><span class="sxs-lookup"><span data-stu-id="802a5-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="802a5-105">Por ejemplo, la propiedad de modo de suavizado determina si se aplica el suavizado de contorno a líneas y curvas conectadas, y la propiedad de transformación universal influye en la posición y rotación de los elementos que se dibujan.</span><span class="sxs-lookup"><span data-stu-id="802a5-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="802a5-106">Un <xref:System.Drawing.Graphics> objeto está asociado a un determinado dispositivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="802a5-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="802a5-107">Cuando se usa un <xref:System.Drawing.Graphics> objeto que se va a dibujar en una ventana, el <xref:System.Drawing.Graphics> objeto también está asociado a esa ventana concreta.</span><span class="sxs-lookup"><span data-stu-id="802a5-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="802a5-108">Un <xref:System.Drawing.Graphics> objeto puede considerarse un contenedor porque contiene un conjunto de propiedades que afectan al dibujo y se vincula a la información específica del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="802a5-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="802a5-109">Puede crear un contenedor secundario dentro de una existente <xref:System.Drawing.Graphics> objeto mediante una llamada a la <xref:System.Drawing.Graphics.BeginContainer%2A> método de dicha <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="802a5-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="802a5-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="802a5-110">In This Section</span></span>  
 [<span data-ttu-id="802a5-111">Administrar el estado de un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="802a5-111">Managing the State of a Graphics Object</span></span>](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="802a5-112">Describe cómo administrar la configuración de calidad, área de recorte y transformaciones de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="802a5-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="802a5-113">Utilizar contenedores de gráficos anidados</span><span class="sxs-lookup"><span data-stu-id="802a5-113">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 <span data-ttu-id="802a5-114">Muestra cómo utilizar los contenedores para controlar el estado de la <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="802a5-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
