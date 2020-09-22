---
title: Error (Instrucción)
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
ms.openlocfilehash: f3f9f5ecb96686fe525e98cf64672d81a3145796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873282"
---
# <a name="error-statement"></a><span data-ttu-id="dae7c-102">Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="dae7c-102">Error Statement</span></span>

<span data-ttu-id="dae7c-103">Simula la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="dae7c-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dae7c-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="dae7c-105">Partes</span><span class="sxs-lookup"><span data-stu-id="dae7c-105">Parts</span></span>  

 `errornumber`  
 <span data-ttu-id="dae7c-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dae7c-106">Required.</span></span> <span data-ttu-id="dae7c-107">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="dae7c-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dae7c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dae7c-108">Remarks</span></span>  

 <span data-ttu-id="dae7c-109">La `Error` instrucción se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="dae7c-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="dae7c-110">En el nuevo código, especialmente al crear objetos, utilice el `Err` método del objeto `Raise` para generar errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dae7c-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="dae7c-111">Si `errornumber` se define, la `Error` instrucción llama al controlador de errores después de que `Err` se asignen los siguientes valores predeterminados a las propiedades del objeto:</span><span class="sxs-lookup"><span data-stu-id="dae7c-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="dae7c-112">Propiedad</span><span class="sxs-lookup"><span data-stu-id="dae7c-112">Property</span></span>|<span data-ttu-id="dae7c-113">Valor</span><span class="sxs-lookup"><span data-stu-id="dae7c-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="dae7c-114">Valor especificado como argumento para la `Error` instrucción.</span><span class="sxs-lookup"><span data-stu-id="dae7c-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="dae7c-115">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="dae7c-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="dae7c-116">Nombre del proyecto de Visual Basic actual.</span><span class="sxs-lookup"><span data-stu-id="dae7c-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="dae7c-117">Expresión de cadena que corresponde al valor devuelto de la `Error` función para el especificado `Number` , si esta cadena existe.</span><span class="sxs-lookup"><span data-stu-id="dae7c-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="dae7c-118">Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").</span><span class="sxs-lookup"><span data-stu-id="dae7c-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="dae7c-119">La unidad, ruta de acceso y nombre de archivo completos del archivo de ayuda Visual Basic adecuado.</span><span class="sxs-lookup"><span data-stu-id="dae7c-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="dae7c-120">El identificador de contexto del archivo de ayuda Visual Basic adecuado para el error correspondiente a la `Number` propiedad.</span><span class="sxs-lookup"><span data-stu-id="dae7c-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="dae7c-121">Cero.</span><span class="sxs-lookup"><span data-stu-id="dae7c-121">Zero.</span></span>|  
  
 <span data-ttu-id="dae7c-122">Si no existe ningún controlador de errores, o si no se habilita ninguno, se crea un mensaje de error y se muestra en las `Err` propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="dae7c-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dae7c-123">Algunas aplicaciones host de Visual Basic no pueden crear objetos.</span><span class="sxs-lookup"><span data-stu-id="dae7c-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="dae7c-124">Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.</span><span class="sxs-lookup"><span data-stu-id="dae7c-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dae7c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dae7c-125">Example</span></span>  

 <span data-ttu-id="dae7c-126">En este ejemplo se utiliza la `Error` instrucción para generar el número de error 11.</span><span class="sxs-lookup"><span data-stu-id="dae7c-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="dae7c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dae7c-127">Requirements</span></span>  

 <span data-ttu-id="dae7c-128">**Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="dae7c-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="dae7c-129">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="dae7c-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae7c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dae7c-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="dae7c-131">Instrucción On Error</span><span class="sxs-lookup"><span data-stu-id="dae7c-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="dae7c-132">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="dae7c-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="dae7c-133">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="dae7c-133">Error Messages</span></span>](../error-messages/index.md)
