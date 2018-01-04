---
title: Herencia visual de formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inheritance
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 857eb737-3602-4d49-bd8b-f70d33ace345
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 177b3034e9afc71a8ecc899364cc4911ef42a1a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-visual-inheritance"></a><span data-ttu-id="003e2-102">Herencia visual de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="003e2-102">Windows Forms Visual Inheritance</span></span>
<span data-ttu-id="003e2-103">En ocasiones, puede decidir que un proyecto llame a un formulario similar al que ha creado en un proyecto anterior.</span><span class="sxs-lookup"><span data-stu-id="003e2-103">Occasionally, you may decide that a project calls for a form similar to one that you have created in a previous project.</span></span> <span data-ttu-id="003e2-104">O puede que desee crear un formulario básico con opciones como una marca de agua o determinado diseño de controles que utilizará de nuevo dentro de un proyecto, incluyendo modificaciones a la plantilla de formulario original con cada iteración.</span><span class="sxs-lookup"><span data-stu-id="003e2-104">Or, you may want to create a basic form with settings such as a watermark or certain control layout that you will then use again within a project, with each iteration containing modifications to the original form template.</span></span> <span data-ttu-id="003e2-105">La herencia de formularios le permite crear un formulario base y, a continuación, heredarlo y realizar modificaciones mientras se conserva la configuración original que necesita.</span><span class="sxs-lookup"><span data-stu-id="003e2-105">Form inheritance enables you to create a base form and then inherit from it and make modifications while preserving whatever original settings you need.</span></span>  
  
 <span data-ttu-id="003e2-106">Puede crear formularios de clase derivada mediante programación o mediante el selector de herencia de objetos visuales.</span><span class="sxs-lookup"><span data-stu-id="003e2-106">You can create derived-class forms programmatically or by using the Visual Inheritance picker.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="003e2-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="003e2-107">In This Section</span></span>  
 [<span data-ttu-id="003e2-108">Cómo: Heredar formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="003e2-108">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 <span data-ttu-id="003e2-109">Proporciona instrucciones para crear formularios heredados en el código.</span><span class="sxs-lookup"><span data-stu-id="003e2-109">Gives directions for creating inherited forms in code.</span></span>  
  
 [<span data-ttu-id="003e2-110">Cómo: Heredar formularios mediante el cuadro de diálogo Selector de herencia</span><span class="sxs-lookup"><span data-stu-id="003e2-110">How to: Inherit Forms Using the Inheritance Picker Dialog Box</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)  
 <span data-ttu-id="003e2-111">Proporciona instrucciones para crear formularios heredados con Selector de herencia.</span><span class="sxs-lookup"><span data-stu-id="003e2-111">Gives directions for creating inherited forms with the Inheritance Picker.</span></span>  
  
 [<span data-ttu-id="003e2-112">Efectos de modificar la apariencia de un formulario base</span><span class="sxs-lookup"><span data-stu-id="003e2-112">Effects of Modifying a Base Form's Appearance</span></span>](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 <span data-ttu-id="003e2-113">Proporciona instrucciones para cambiar los controles de un formulario base y sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="003e2-113">Gives directions for changing a base form's controls and their properties.</span></span>  
  
 [<span data-ttu-id="003e2-114">Tutorial: Demostración de la herencia visual</span><span class="sxs-lookup"><span data-stu-id="003e2-114">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 <span data-ttu-id="003e2-115">Describe cómo crear un formulario base de Windows Form y compilarlo en la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="003e2-115">Describes how to create a base Windows Form and compile it into a class library.</span></span> <span data-ttu-id="003e2-116">Importará la biblioteca de clases en otro proyecto y creará un nuevo formulario que herede del formulario base.</span><span class="sxs-lookup"><span data-stu-id="003e2-116">You will import this class library into another project, and create a new form that inherits from the base form.</span></span>  
  
 [<span data-ttu-id="003e2-117">Cómo: Utilizar las propiedades Modifiers y GenerateMember</span><span class="sxs-lookup"><span data-stu-id="003e2-117">How to: Use the Modifiers and GenerateMember Properties</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-the-modifiers-and-generatemember-properties.md)  
 <span data-ttu-id="003e2-118">Proporciona instrucciones para utilizar las propiedades `GenerateMember` y `Modifiers`, que son pertinentes cuando el Diseñador de Windows Forms genera una variable de miembro para un componente.</span><span class="sxs-lookup"><span data-stu-id="003e2-118">Gives directions for using the `GenerateMember` and `Modifiers` properties, which are relevant when the Windows Forms Designer generates a member variable for a component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="003e2-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="003e2-119">Related Sections</span></span>  
 [<span data-ttu-id="003e2-120">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003e2-120">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 <span data-ttu-id="003e2-121">Describe cómo definir clases de Visual Basic que sirvan como base para otras clases.</span><span class="sxs-lookup"><span data-stu-id="003e2-121">Describes how to define Visual Basic classes that serve as the basis for other classes.</span></span>  
  
 [<span data-ttu-id="003e2-122">class</span><span class="sxs-lookup"><span data-stu-id="003e2-122">class</span></span>](~/docs/csharp/language-reference/keywords/class.md)  
 <span data-ttu-id="003e2-123">Describe el enfoque de clases de C#, en el que se permite la herencia simple.</span><span class="sxs-lookup"><span data-stu-id="003e2-123">Describes the C# approach of classes, in which single inheritance is allowed.</span></span>  
  
 [<span data-ttu-id="003e2-124">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="003e2-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="003e2-125">Enumera los problemas habituales que se producen con los controladores de eventos en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="003e2-125">Lists common issues that arise with event handlers in inherited components</span></span>
