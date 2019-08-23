---
title: Instrucción error (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944454"
---
# <a name="error-statement"></a><span data-ttu-id="f498d-102">Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f498d-102">Error Statement</span></span>
<span data-ttu-id="f498d-103">Simula la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="f498d-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f498d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f498d-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="f498d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f498d-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="f498d-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f498d-106">Required.</span></span> <span data-ttu-id="f498d-107">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="f498d-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f498d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f498d-108">Remarks</span></span>  
 <span data-ttu-id="f498d-109">La `Error` instrucción se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="f498d-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="f498d-110">En el nuevo código, especialmente al crear objetos, utilice `Err` el método `Raise` del objeto para generar errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f498d-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="f498d-111">Si `errornumber` se define, la `Error` instrucción llama al controlador de errores `Err` después de que se asignen los siguientes valores predeterminados a las propiedades del objeto:</span><span class="sxs-lookup"><span data-stu-id="f498d-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="f498d-112">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f498d-112">Property</span></span>|<span data-ttu-id="f498d-113">Value</span><span class="sxs-lookup"><span data-stu-id="f498d-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="f498d-114">Valor especificado como argumento para `Error` la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f498d-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="f498d-115">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="f498d-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="f498d-116">Nombre del proyecto de Visual Basic actual.</span><span class="sxs-lookup"><span data-stu-id="f498d-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="f498d-117">Expresión de cadena que corresponde al valor devuelto `Error` de la función para `Number`el especificado, si esta cadena existe.</span><span class="sxs-lookup"><span data-stu-id="f498d-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="f498d-118">Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").</span><span class="sxs-lookup"><span data-stu-id="f498d-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="f498d-119">La unidad, ruta de acceso y nombre de archivo completos del archivo de ayuda Visual Basic adecuado.</span><span class="sxs-lookup"><span data-stu-id="f498d-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="f498d-120">El identificador de contexto del archivo de ayuda Visual Basic adecuado para el error `Number` correspondiente a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f498d-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="f498d-121">Nulo.</span><span class="sxs-lookup"><span data-stu-id="f498d-121">Zero.</span></span>|  
  
 <span data-ttu-id="f498d-122">Si no existe ningún controlador de errores, o si no se habilita ninguno, se crea un mensaje de error `Err` y se muestra en las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="f498d-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f498d-123">Algunas aplicaciones host de Visual Basic no pueden crear objetos.</span><span class="sxs-lookup"><span data-stu-id="f498d-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="f498d-124">Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.</span><span class="sxs-lookup"><span data-stu-id="f498d-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f498d-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f498d-125">Example</span></span>  
 <span data-ttu-id="f498d-126">En este ejemplo se `Error` utiliza la instrucción para generar el número de error 11.</span><span class="sxs-lookup"><span data-stu-id="f498d-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="f498d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f498d-127">Requirements</span></span>  
 <span data-ttu-id="f498d-128">**Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="f498d-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="f498d-129">**Assembl** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="f498d-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f498d-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f498d-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="f498d-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f498d-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="f498d-132">Resume (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f498d-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="f498d-133">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="f498d-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
