---
title: Proporcionar información de accesibilidad de controles en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 3067c90978e6ebd680d10c1c4f9db131f19c9e44
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614752"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="5b16b-102">Proporcionar información de accesibilidad de controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b16b-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="5b16b-103">Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="5b16b-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="5b16b-104">Algunos ejemplos son los lectores de pantalla para invidentes y las utilidades de entrada de voz para las personas que usan comandos verbales en lugar del mouse o el teclado.</span><span class="sxs-lookup"><span data-stu-id="5b16b-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="5b16b-105">Estas ayudas de accesibilidad interactúan con las propiedades de accesibilidad que exponen los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5b16b-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="5b16b-106">Dichas propiedades son:</span><span class="sxs-lookup"><span data-stu-id="5b16b-106">These properties are:</span></span>  
  
- <span data-ttu-id="5b16b-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="5b16b-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="5b16b-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="5b16b-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="5b16b-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="5b16b-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="5b16b-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="5b16b-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="5b16b-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="5b16b-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="5b16b-112">AccessibilityObject Property</span><span class="sxs-lookup"><span data-stu-id="5b16b-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="5b16b-113">Esta propiedad de solo lectura contiene una instancia de la <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="5b16b-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="5b16b-114">La propiedad **AccessibleObject** implementa la interfaz de <xref:Accessibility.IAccessible> , que proporciona información acerca de la descripción, la ubicación de la pantalla, las funciones de desplazamiento y valor del control.</span><span class="sxs-lookup"><span data-stu-id="5b16b-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="5b16b-115">El diseñador establece este valor cuando se agrega el control al formulario.</span><span class="sxs-lookup"><span data-stu-id="5b16b-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="5b16b-116">Propiedad AccessibleDefaultActionDescription</span><span class="sxs-lookup"><span data-stu-id="5b16b-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="5b16b-117">Esta cadena describe la acción del control.</span><span class="sxs-lookup"><span data-stu-id="5b16b-117">This string describes the action of the control.</span></span> <span data-ttu-id="5b16b-118">No aparece en la ventana Propiedades y es posible que solo se establezca en el código.</span><span class="sxs-lookup"><span data-stu-id="5b16b-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="5b16b-119">Los ejemplos siguientes establecen esta propiedad para un control de botón:</span><span class="sxs-lookup"><span data-stu-id="5b16b-119">The following example sets this property for a button control:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="5b16b-120">Propiedad AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="5b16b-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="5b16b-121">Esta cadena describe el control.</span><span class="sxs-lookup"><span data-stu-id="5b16b-121">This string describes the control.</span></span> <span data-ttu-id="5b16b-122">Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b16b-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="5b16b-123">Propiedad AccessibleName</span><span class="sxs-lookup"><span data-stu-id="5b16b-123">AccessibleName Property</span></span>  
 <span data-ttu-id="5b16b-124">Este es el nombre de un control notificado a las ayudas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="5b16b-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="5b16b-125">Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b16b-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="5b16b-126">Propiedad AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="5b16b-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="5b16b-127">Esta propiedad, que contiene una <xref:System.Windows.Forms.AccessibleRole> , describe el rol de la interfaz de usuario del control.</span><span class="sxs-lookup"><span data-stu-id="5b16b-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="5b16b-128">Un nuevo control tiene el valor establecido en `Default`.</span><span class="sxs-lookup"><span data-stu-id="5b16b-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="5b16b-129">Esto significa que, de forma predeterminada, un control **Button** actúa como un **Button**.</span><span class="sxs-lookup"><span data-stu-id="5b16b-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="5b16b-130">Es posible que quiera restablecer esta propiedad si un control tiene otro rol.</span><span class="sxs-lookup"><span data-stu-id="5b16b-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="5b16b-131">Por ejemplo, puede que esté usando un control **PictureBox** como un control **Chart**y quiera que las ayudas de accesibilidad informen del rol como **Chart**y no como **PictureBox**.</span><span class="sxs-lookup"><span data-stu-id="5b16b-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="5b16b-132">Es posible que también quiera especificar esta propiedad para los controles personalizados que ha desarrollado.</span><span class="sxs-lookup"><span data-stu-id="5b16b-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="5b16b-133">Esta propiedad se puede establecer en la ventana Propiedades o en el código de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b16b-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b16b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b16b-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
