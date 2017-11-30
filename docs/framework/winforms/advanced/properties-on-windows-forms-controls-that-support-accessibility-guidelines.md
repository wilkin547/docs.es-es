---
title: Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ca18b35b90b028054e68a0a14fecc819a6c20b9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="c0ae1-102">Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c0ae1-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="c0ae1-103">Controles en el cuadro de herramientas estándar de Windows Forms admiten muchas de las directrices de accesibilidad, incluida la exposición el foco del teclado y de los elementos de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="c0ae1-104">Planear con antelación para mejorar la accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c0ae1-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="c0ae1-105">Propiedades de los controles se pueden utilizar para admitir otras directrices de accesibilidad, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="c0ae1-106">Además, es recomendable utilizar menús para proporcionar acceso a características del programa.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="c0ae1-107">Propiedad de control</span><span class="sxs-lookup"><span data-stu-id="c0ae1-107">Control Property</span></span>|<span data-ttu-id="c0ae1-108">Consideraciones para la accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c0ae1-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="c0ae1-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="c0ae1-109">AccessibleDescription</span></span>|<span data-ttu-id="c0ae1-110">La descripción se notifica a las ayudas de accesibilidad como lectores de pantalla.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="c0ae1-111">Las ayudas de accesibilidad son programas y dispositivos especializados que ayudan a las personas con discapacidades a usar los equipos de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="c0ae1-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="c0ae1-112">AccessibleName</span></span>|<span data-ttu-id="c0ae1-113">El nombre que se informará a las ayudas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="c0ae1-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="c0ae1-114">AccessibleRole</span></span>|<span data-ttu-id="c0ae1-115">Describe el uso del elemento de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="c0ae1-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="c0ae1-116">TabIndex</span></span>|<span data-ttu-id="c0ae1-117">Crea una ruta razonable para desplazarse a través del formulario.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="c0ae1-118">Es importante para los controles sin etiquetas intrínsecas, como cuadros de texto, para que sus etiquetas asociadas precedan inmediatamente a ellos en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="c0ae1-119">Texto</span><span class="sxs-lookup"><span data-stu-id="c0ae1-119">Text</span></span>|<span data-ttu-id="c0ae1-120">Use el carácter "&" para crear teclas de acceso.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="c0ae1-121">Utilizando las teclas de acceso forma parte de proporcionar acceso mediante teclado documentado a las características.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="c0ae1-122">Tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="c0ae1-122">Font Size</span></span>|<span data-ttu-id="c0ae1-123">Si el tamaño de fuente no es ajustable, a continuación, se debe establecer en 10 puntos o más.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="c0ae1-124">Una vez que se establece el tamaño de fuente del formulario, todos los controles que se agregan posteriormente al formulario tendrán el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="c0ae1-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="c0ae1-125">Forecolor</span></span>|<span data-ttu-id="c0ae1-126">Si esta propiedad se establece en el valor predeterminado, las preferencias del usuario color se usará en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="c0ae1-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="c0ae1-127">Backcolor</span></span>|<span data-ttu-id="c0ae1-128">Si esta propiedad se establece en el valor predeterminado, las preferencias del usuario color se usará en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="c0ae1-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="c0ae1-129">BackgroundImage</span></span>|<span data-ttu-id="c0ae1-130">Deje esta propiedad en blanco para mejorar la legibilidad del texto.</span><span class="sxs-lookup"><span data-stu-id="c0ae1-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0ae1-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0ae1-131">See Also</span></span>  
 [<span data-ttu-id="c0ae1-132">Tutorial: Crear una aplicación accesible basada en Windows</span><span class="sxs-lookup"><span data-stu-id="c0ae1-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
