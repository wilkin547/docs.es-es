---
title: Información general de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: a95086645771de61cfc859e34b225992bc16eac9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103940"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="19d63-102">Información general de gráficos</span><span class="sxs-lookup"><span data-stu-id="19d63-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="19d63-103">es una interfaz de programación de aplicaciones (API) que forma el subsistema del sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="19d63-103">is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="19d63-104">es responsable de mostrar información en pantallas e impresoras.</span><span class="sxs-lookup"><span data-stu-id="19d63-104">is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="19d63-105">Como sugiere su nombre, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es la sucesora de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], la interfaz de dispositivo gráfico incluida en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="19d63-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="19d63-106">Interfaz de clases administradas</span><span class="sxs-lookup"><span data-stu-id="19d63-106">Managed Class Interface</span></span>  
 <span data-ttu-id="19d63-107">El [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API se expone a través de un conjunto de clases implementadas como código administrado.</span><span class="sxs-lookup"><span data-stu-id="19d63-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="19d63-108">Este conjunto de clases se denomina el *interfaz de clases administradas* a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19d63-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="19d63-109">Los espacios de nombres siguientes constituyen la interfaz de clases administradas:</span><span class="sxs-lookup"><span data-stu-id="19d63-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="19d63-110">Con una interfaz de dispositivo de gráficos, como [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede mostrar información en una pantalla o impresora sin tener que preocuparse sobre los detalles de un dispositivo de presentación determinado.</span><span class="sxs-lookup"><span data-stu-id="19d63-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="19d63-111">El programador llama a métodos proporcionados por clases [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19d63-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="19d63-112">A su vez, estos métodos realizan las llamadas adecuadas a controladores de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="19d63-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="19d63-113">aísla la aplicación del hardware gráfico.</span><span class="sxs-lookup"><span data-stu-id="19d63-113">insulates the application from the graphics hardware.</span></span> <span data-ttu-id="19d63-114">Se trata del aislamiento que permite al programador crear aplicaciones independientes del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19d63-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d63-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="19d63-115">See also</span></span>

- <span data-ttu-id="19d63-116">[Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])</span><span class="sxs-lookup"><span data-stu-id="19d63-116">[Graphics Overview](graphics-overview-windows-forms.md)</span></span>
