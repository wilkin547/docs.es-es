---
title: Errores en tiempo de diseño en el Diseñador de Windows Forms
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015968"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="e797c-102">Errores en tiempo de diseño en el Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e797c-102">Design-time errors in the Windows Forms Designer</span></span>

<span data-ttu-id="e797c-103">En este tema se explica el significado y el uso de la lista de errores en tiempo de diseño que aparece en Visual Studio cuando no se puede cargar el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e797c-103">This topic explains the meaning and use of the design-time error list that appears in Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="e797c-104">Si esta lista de errores aparece, no debe interpretarse como un error del diseñador, sino como una ayuda para corregir errores en el código.</span><span class="sxs-lookup"><span data-stu-id="e797c-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>

<span data-ttu-id="e797c-105">Un conocimiento básico de esta lista de errores le ayudará a depurar las aplicaciones brindando información detallada sobre los errores y sugerir posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="e797c-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>

## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="e797c-106">La interfaz de la lista de errores en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="e797c-106">The design-time error list interface</span></span>

<span data-ttu-id="e797c-107">Si no se puede cargar el Diseñador de Windows Forms, aparece una lista de errores en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="e797c-107">If the Windows Forms Designer fails to load, an error list appears in the designer.</span></span> <span data-ttu-id="e797c-108">Los errores se agrupan en categorías.</span><span class="sxs-lookup"><span data-stu-id="e797c-108">The errors are grouped into categories.</span></span> <span data-ttu-id="e797c-109">Por ejemplo, si tiene cuatro instancias de variables no declaradas, se agruparán en la misma categoría de error.</span><span class="sxs-lookup"><span data-stu-id="e797c-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="e797c-110">Cada categoría de error incluye una breve descripción del error.</span><span class="sxs-lookup"><span data-stu-id="e797c-110">Each error category includes a brief description that summarizes the error.</span></span>

<span data-ttu-id="e797c-111">Puede expandir o contraer una categoría de error haciendo clic en el encabezado de la categoría de error o en el botón de contenido adicional de expandir o contraer.</span><span class="sxs-lookup"><span data-stu-id="e797c-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="e797c-112">Al expandir una categoría de error, se muestra la ayuda adicional siguiente:</span><span class="sxs-lookup"><span data-stu-id="e797c-112">When you expand an error category, the following additional help is displayed:</span></span>

- <span data-ttu-id="e797c-113">Instancias del error.</span><span class="sxs-lookup"><span data-stu-id="e797c-113">Instances of this error.</span></span>

- <span data-ttu-id="e797c-114">Ayuda con el error.</span><span class="sxs-lookup"><span data-stu-id="e797c-114">Help with this error.</span></span>

- <span data-ttu-id="e797c-115">Entradas del foro sobre el error.</span><span class="sxs-lookup"><span data-stu-id="e797c-115">Forum posts about this error.</span></span>

### <a name="instances-of-this-error"></a><span data-ttu-id="e797c-116">Instancias de este error</span><span class="sxs-lookup"><span data-stu-id="e797c-116">Instances of this error</span></span>

<span data-ttu-id="e797c-117">La lista de ayuda adicional muestra todas las instancias del error en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="e797c-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="e797c-118">Muchos errores incluyen una ubicación exacta en el formato siguiente: *[nombre de proyecto]* *[nombre del formulario]* línea: *[número de línea]* columna: *[número de columna]* .</span><span class="sxs-lookup"><span data-stu-id="e797c-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="e797c-119">El vínculo **Ir al código** le lleva a la ubicación del código donde se produce el error.</span><span class="sxs-lookup"><span data-stu-id="e797c-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>

<span data-ttu-id="e797c-120">Si se asocia una pila de llamadas al error, puede hacer clic en el vínculo **Mostrar pila de llamadas**, lo que amplía aún más el error para mostrar la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e797c-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="e797c-121">El examen de la pila puede ofrecer información valiosa sobre depuración.</span><span class="sxs-lookup"><span data-stu-id="e797c-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="e797c-122">Por ejemplo, puede realizar el seguimiento de las funciones que se llamaron antes de producirse el error.</span><span class="sxs-lookup"><span data-stu-id="e797c-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="e797c-123">La pila de llamadas es seleccionable para que se pueda copiar y guardarla.</span><span class="sxs-lookup"><span data-stu-id="e797c-123">The call stack is selectable so that you can copy and save it.</span></span>

> [!NOTE]
> <span data-ttu-id="e797c-124">En Visual Basic, la lista de errores en tiempo de diseño no muestra más que un error, pero puede mostrar varias instancias del mismo error.</span><span class="sxs-lookup"><span data-stu-id="e797c-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="e797c-125">En Visual C++, los errores no tienen vínculos para ir al código ni vínculos de números de línea.</span><span class="sxs-lookup"><span data-stu-id="e797c-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>

### <a name="forum-posts-about-this-error"></a><span data-ttu-id="e797c-126">Entradas del foro sobre este error</span><span class="sxs-lookup"><span data-stu-id="e797c-126">Forum posts about this error</span></span>

<span data-ttu-id="e797c-127">La ayuda adicional incluye un vínculo a las entradas del Foro relacionadas con el error.</span><span class="sxs-lookup"><span data-stu-id="e797c-127">The additional help includes a link to forum posts related to the error.</span></span> <span data-ttu-id="e797c-128">Los foros se buscan por la cadena del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="e797c-128">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="e797c-129">También puede intentar buscar en los foros siguientes:</span><span class="sxs-lookup"><span data-stu-id="e797c-129">You can also try searching on the following forums:</span></span>

- [<span data-ttu-id="e797c-130">Foro de Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e797c-130">Windows Forms Designer forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [<span data-ttu-id="e797c-131">Foro de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e797c-131">Windows Forms forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a><span data-ttu-id="e797c-132">Omitir y continuar</span><span class="sxs-lookup"><span data-stu-id="e797c-132">Ignore and continue</span></span>

<span data-ttu-id="e797c-133">Puede omitir la condición de error y seguir cargando el diseñador.</span><span class="sxs-lookup"><span data-stu-id="e797c-133">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="e797c-134">La elección de esta acción puede dar lugar a un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="e797c-134">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="e797c-135">Por ejemplo, puede que no aparezcan controles en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="e797c-135">For example, controls may not appear on the design surface.</span></span>

## <a name="see-also"></a><span data-ttu-id="e797c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e797c-136">See also</span></span>

- <span data-ttu-id="e797c-137">[Solución de problemas de desarrollo en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e797c-137">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
- [<span data-ttu-id="e797c-138">Solución de problemas relacionados con la creación de controles y componentes</span><span class="sxs-lookup"><span data-stu-id="e797c-138">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)
- [<span data-ttu-id="e797c-139">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="e797c-139">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="e797c-140">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100)) (Mensajes de error del Diseñador de Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e797c-140">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span></span>
