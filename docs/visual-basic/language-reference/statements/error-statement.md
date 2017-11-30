---
title: "Error (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cd3245fd3e9e62b1b6443e9787c97808a0d179d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="error-statement"></a><span data-ttu-id="de825-102">Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="de825-102">Error Statement</span></span>
<span data-ttu-id="de825-103">Simula la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="de825-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de825-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="de825-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="de825-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="de825-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="de825-106">Required.</span></span> <span data-ttu-id="de825-107">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="de825-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de825-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de825-108">Remarks</span></span>  
 <span data-ttu-id="de825-109">El `Error` instrucción se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="de825-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="de825-110">En el nuevo código, especialmente al crear objetos, utilice la `Err` del objeto `Raise` método para generar errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="de825-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="de825-111">Si `errornumber` se define, el `Error` instrucción llama al controlador de errores después de las propiedades de la `Err` objeto se asignan los valores predeterminados siguientes:</span><span class="sxs-lookup"><span data-stu-id="de825-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="de825-112">Propiedad</span><span class="sxs-lookup"><span data-stu-id="de825-112">Property</span></span>|<span data-ttu-id="de825-113">Valor</span><span class="sxs-lookup"><span data-stu-id="de825-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="de825-114">El valor especificado como argumento para `Error` instrucción.</span><span class="sxs-lookup"><span data-stu-id="de825-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="de825-115">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="de825-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="de825-116">Nombre del proyecto actual de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="de825-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="de825-117">Corresponde al valor devuelto de una expresión de cadena del `Error` función para el elemento especificado `Number`, si esta cadena no existe.</span><span class="sxs-lookup"><span data-stu-id="de825-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="de825-118">Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").</span><span class="sxs-lookup"><span data-stu-id="de825-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="de825-119">El nombre completo con unidad, ruta de acceso y nombre de archivo del archivo de Ayuda de Visual Basic apropiado.</span><span class="sxs-lookup"><span data-stu-id="de825-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="de825-120">La Ayuda de Visual Basic correspondiente archivo de Id. de contexto para el error correspondiente a la `Number` propiedad.</span><span class="sxs-lookup"><span data-stu-id="de825-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="de825-121">Es cero.</span><span class="sxs-lookup"><span data-stu-id="de825-121">Zero.</span></span>|  
  
 <span data-ttu-id="de825-122">Si no hay ningún controlador de error existe, o si ninguno está habilitado, se crea un mensaje de error y se muestra en la `Err` propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="de825-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de825-123">Algunas aplicaciones de host de Visual Basic no pueden crear objetos.</span><span class="sxs-lookup"><span data-stu-id="de825-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="de825-124">Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.</span><span class="sxs-lookup"><span data-stu-id="de825-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de825-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de825-125">Example</span></span>  
 <span data-ttu-id="de825-126">Este ejemplo se utiliza la `Error` instrucción que se va a generar el error número 11.</span><span class="sxs-lookup"><span data-stu-id="de825-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="de825-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de825-127">Requirements</span></span>  
 <span data-ttu-id="de825-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="de825-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="de825-129">**Ensamblado:** biblioteca de tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="de825-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de825-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="de825-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [<span data-ttu-id="de825-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="de825-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [<span data-ttu-id="de825-132">Resume (instrucción)</span><span class="sxs-lookup"><span data-stu-id="de825-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="de825-133">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="de825-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
