---
title: Proporcionar información de accesibilidad de controles en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 0f589f37d79c9ec8d55153aac4c846726a379055
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948027"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="a339c-102">Proporcionar información de accesibilidad de controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a339c-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="a339c-103">Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="a339c-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="a339c-104">Algunos ejemplos son los lectores de pantalla para invidentes y las utilidades de entrada de voz para las personas que usan comandos verbales en lugar del mouse o el teclado.</span><span class="sxs-lookup"><span data-stu-id="a339c-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="a339c-105">Estas ayudas de accesibilidad interactúan con las propiedades de accesibilidad que exponen los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a339c-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="a339c-106">Dichas propiedades son:</span><span class="sxs-lookup"><span data-stu-id="a339c-106">These properties are:</span></span>  
  
- <span data-ttu-id="a339c-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="a339c-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="a339c-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="a339c-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="a339c-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="a339c-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="a339c-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="a339c-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="a339c-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="a339c-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="a339c-112">AccessibilityObject Property</span><span class="sxs-lookup"><span data-stu-id="a339c-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="a339c-113">Esta propiedad de solo lectura contiene una instancia de la <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="a339c-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="a339c-114">La propiedad **AccessibleObject** implementa la interfaz de <xref:Accessibility.IAccessible> , que proporciona información acerca de la descripción, la ubicación de la pantalla, las funciones de desplazamiento y valor del control.</span><span class="sxs-lookup"><span data-stu-id="a339c-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="a339c-115">El diseñador establece este valor cuando se agrega el control al formulario.</span><span class="sxs-lookup"><span data-stu-id="a339c-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="a339c-116">Propiedad AccessibleDefaultActionDescription</span><span class="sxs-lookup"><span data-stu-id="a339c-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="a339c-117">Esta cadena describe la acción del control.</span><span class="sxs-lookup"><span data-stu-id="a339c-117">This string describes the action of the control.</span></span> <span data-ttu-id="a339c-118">No aparece en la ventana Propiedades y es posible que solo se establezca en el código.</span><span class="sxs-lookup"><span data-stu-id="a339c-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="a339c-119">Los ejemplos siguientes establecen esta propiedad para un control de botón:</span><span class="sxs-lookup"><span data-stu-id="a339c-119">The following example sets this property for a button control:</span></span>  
  
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
  
## <a name="accessibledescription-property"></a><span data-ttu-id="a339c-120">Propiedad AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a339c-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="a339c-121">Esta cadena describe el control.</span><span class="sxs-lookup"><span data-stu-id="a339c-121">This string describes the control.</span></span> <span data-ttu-id="a339c-122">Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a339c-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="a339c-123">Propiedad AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a339c-123">AccessibleName Property</span></span>  
 <span data-ttu-id="a339c-124">Este es el nombre de un control notificado a las ayudas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="a339c-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="a339c-125">Se puede establecer en la ventana Propiedades o en el código de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a339c-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="a339c-126">Propiedad AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="a339c-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="a339c-127">Esta propiedad, que contiene una <xref:System.Windows.Forms.AccessibleRole> , describe el rol de la interfaz de usuario del control.</span><span class="sxs-lookup"><span data-stu-id="a339c-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="a339c-128">Un nuevo control tiene el valor establecido en `Default`.</span><span class="sxs-lookup"><span data-stu-id="a339c-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="a339c-129">Esto significa que, de forma predeterminada, un control **Button** actúa como un **Button**.</span><span class="sxs-lookup"><span data-stu-id="a339c-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="a339c-130">Es posible que quiera restablecer esta propiedad si un control tiene otro rol.</span><span class="sxs-lookup"><span data-stu-id="a339c-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="a339c-131">Por ejemplo, puede que esté usando un control **PictureBox** como un control **Chart**y quiera que las ayudas de accesibilidad informen del rol como **Chart**y no como **PictureBox**.</span><span class="sxs-lookup"><span data-stu-id="a339c-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="a339c-132">Es posible que también quiera especificar esta propiedad para los controles personalizados que ha desarrollado.</span><span class="sxs-lookup"><span data-stu-id="a339c-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="a339c-133">Esta propiedad se puede establecer en la ventana Propiedades o en el código de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a339c-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a339c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a339c-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
