---
title: Información general de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505323"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="3364a-102">Información general de gráficos</span><span class="sxs-lookup"><span data-stu-id="3364a-102">Overview of Graphics</span></span>
<span data-ttu-id="3364a-103">GDI + es una interfaz de programación de aplicaciones (API) que forma el subsistema del sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3364a-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="3364a-104">GDI + es responsable de mostrar información en pantallas e impresoras.</span><span class="sxs-lookup"><span data-stu-id="3364a-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="3364a-105">Como sugiere su nombre, GDI + es la sucesora de GDI, la interfaz de dispositivo gráfico incluida en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="3364a-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="3364a-106">Interfaz de clases administradas</span><span class="sxs-lookup"><span data-stu-id="3364a-106">Managed Class Interface</span></span>  
 <span data-ttu-id="3364a-107">La API de GDI + se expone a través de un conjunto de clases implementadas como código administrado.</span><span class="sxs-lookup"><span data-stu-id="3364a-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="3364a-108">Este conjunto de clases se denomina el *interfaz de clases administradas* a GDI +.</span><span class="sxs-lookup"><span data-stu-id="3364a-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="3364a-109">Los espacios de nombres siguientes constituyen la interfaz de clases administradas:</span><span class="sxs-lookup"><span data-stu-id="3364a-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="3364a-110">Con una interfaz de dispositivo de gráficos, como GDI +, puede mostrar información en una pantalla o impresora sin tener que preocuparse sobre los detalles de un dispositivo de presentación determinado.</span><span class="sxs-lookup"><span data-stu-id="3364a-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="3364a-111">El programador realiza las llamadas a métodos proporcionados por las clases de GDI +.</span><span class="sxs-lookup"><span data-stu-id="3364a-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="3364a-112">A su vez, estos métodos realizan las llamadas adecuadas a controladores de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="3364a-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="3364a-113">GDI + aísla la aplicación del hardware gráfico.</span><span class="sxs-lookup"><span data-stu-id="3364a-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="3364a-114">Se trata del aislamiento que permite al programador crear aplicaciones independientes del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3364a-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3364a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3364a-115">See also</span></span>

- <span data-ttu-id="3364a-116">[Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])</span><span class="sxs-lookup"><span data-stu-id="3364a-116">[Graphics Overview](graphics-overview-windows-forms.md)</span></span>
