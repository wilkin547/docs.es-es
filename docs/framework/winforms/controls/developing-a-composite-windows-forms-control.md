---
title: Desarrollar un control de formularios Windows Forms compuesto
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: dc038e5a1858025007ef737397521bfea1b93b97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528304"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="00ccb-102">Desarrollar un control de formularios Windows Forms compuesto</span><span class="sxs-lookup"><span data-stu-id="00ccb-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="00ccb-103">Puede desarrollar un control de Windows Forms compuesto mediante la combinación de otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="00ccb-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="00ccb-104">Controles compuestos que derivan de <xref:System.Web.UI.UserControl> se denominan controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="00ccb-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="00ccb-105">La clase base, <xref:System.Windows.Forms.UserControl>, proporciona el enrutamiento de teclado de los controles secundarios, lo que asegura que puedan recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="00ccb-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="00ccb-106">Para obtener un ejemplo de un control de usuario, consulte la <xref:System.Windows.Forms.UserControl> en [Cómo: aplicar atributos en controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="00ccb-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="00ccb-107">El Diseñador de Windows Forms de [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] proporciona una buena compatibilidad en tiempo de diseño para la creación de controles de usuario. </span><span class="sxs-lookup"><span data-stu-id="00ccb-107">The Windows Forms designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] provides rich design-time support for authoring user controls.</span></span>  
  
-   <span data-ttu-id="00ccb-108">[Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-108">[How to: Display a Control in the Choose Toolbox Items Dialog Box](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-109">[Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-109">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-110">[Tutorial: Heredar de un control de Windows Forms con Visual C#](http://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438)</span><span class="sxs-lookup"><span data-stu-id="00ccb-110">[Walkthrough: Inheriting from a Windows Forms Control with Visual C#](http://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438))</span></span>  
  
-   <span data-ttu-id="00ccb-111">[Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-111">[How to: Provide a Toolbox Bitmap for a Control](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-112">[Cómo: Heredar de controles de Windows Forms existentes](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-112">[How to: Inherit from Existing Windows Forms Controls](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-113">[Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-113">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-114">[Cómo: Heredar de la clase control](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-114">[How to: Inherit from the Control Class](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-115">[Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-115">[How to: Test the Run-Time Behavior of a UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-116">[Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-116">[How to: Align a Control to the Edges of Forms at Design Time](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-117">[cómo: Heredar de la clase UserControl](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-117">[How to: Inherit from the UserControl Class](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-118">[Cómo: Crear controles para Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-118">[How to: Author Controls for Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-119">[Cómo: Crear controles compuestos](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-119">[How to: Author Composite Controls](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-120">[Tutorial: Crear un control compuesto con Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-120">[Walkthrough: Authoring a Composite Control with Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-121">[Tutorial: Crear un control compuesto con Visual C#](http://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f)</span><span class="sxs-lookup"><span data-stu-id="00ccb-121">[Walkthrough: Authoring a Composite Control with Visual C#](http://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f))</span></span>  
  
-   <span data-ttu-id="00ccb-122">[Tutorial: Heredar de un control de Windows Forms con Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-122">[Walkthrough: Inheriting from a Windows Forms Control with Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-123">[Cómo: Crear un control de Windows Forms que aproveche las características de tiempo de diseño](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-123">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="00ccb-124">[Cómo: Crear un control de Windows Forms que aproveche las características en tiempo de diseño](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="00ccb-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ccb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ccb-125">See Also</span></span>  
 [<span data-ttu-id="00ccb-126">Aplicar atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00ccb-126">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="00ccb-127">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="00ccb-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="00ccb-128">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="00ccb-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
