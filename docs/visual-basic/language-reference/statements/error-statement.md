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
ms.openlocfilehash: c7b2adfe7f6b6ff5e89598cb318a90c51595ff6f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583379"
---
# <a name="error-statement"></a><span data-ttu-id="6b290-102">Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b290-102">Error Statement</span></span>
<span data-ttu-id="6b290-103">Simula la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="6b290-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b290-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b290-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="6b290-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6b290-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="6b290-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6b290-106">Required.</span></span> <span data-ttu-id="6b290-107">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="6b290-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b290-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b290-108">Remarks</span></span>  
 <span data-ttu-id="6b290-109">La instrucción `Error` se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="6b290-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="6b290-110">En el nuevo código, especialmente al crear objetos, utilice el método `Raise` del objeto `Err` para generar errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6b290-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="6b290-111">Si se define `errornumber`, la instrucción `Error` llama al controlador de errores después de que se asignen los siguientes valores predeterminados a las propiedades del objeto `Err`:</span><span class="sxs-lookup"><span data-stu-id="6b290-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="6b290-112">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="6b290-112">Property</span></span>|<span data-ttu-id="6b290-113">Valor</span><span class="sxs-lookup"><span data-stu-id="6b290-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="6b290-114">Valor especificado como argumento para `Error` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6b290-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="6b290-115">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="6b290-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="6b290-116">Nombre del proyecto de Visual Basic actual.</span><span class="sxs-lookup"><span data-stu-id="6b290-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="6b290-117">Expresión de cadena que corresponde al valor devuelto de la función `Error` para el `Number` especificado, si esta cadena existe.</span><span class="sxs-lookup"><span data-stu-id="6b290-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="6b290-118">Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").</span><span class="sxs-lookup"><span data-stu-id="6b290-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="6b290-119">La unidad, ruta de acceso y nombre de archivo completos del archivo de ayuda Visual Basic adecuado.</span><span class="sxs-lookup"><span data-stu-id="6b290-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="6b290-120">El identificador de contexto del archivo de ayuda Visual Basic adecuado para el error correspondiente a la propiedad `Number`.</span><span class="sxs-lookup"><span data-stu-id="6b290-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="6b290-121">Nulo.</span><span class="sxs-lookup"><span data-stu-id="6b290-121">Zero.</span></span>|  
  
 <span data-ttu-id="6b290-122">Si no existe ningún controlador de errores, o si no se habilita ninguno, se crea un mensaje de error que se muestra en las propiedades del objeto `Err`.</span><span class="sxs-lookup"><span data-stu-id="6b290-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b290-123">Algunas aplicaciones host de Visual Basic no pueden crear objetos.</span><span class="sxs-lookup"><span data-stu-id="6b290-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="6b290-124">Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.</span><span class="sxs-lookup"><span data-stu-id="6b290-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b290-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b290-125">Example</span></span>  
 <span data-ttu-id="6b290-126">En este ejemplo se utiliza la instrucción `Error` para generar el número de error 11.</span><span class="sxs-lookup"><span data-stu-id="6b290-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="6b290-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b290-127">Requirements</span></span>  
 <span data-ttu-id="6b290-128">**Espacio de nombres:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="6b290-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="6b290-129">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="6b290-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b290-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b290-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="6b290-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b290-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="6b290-132">Resume (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6b290-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="6b290-133">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="6b290-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
