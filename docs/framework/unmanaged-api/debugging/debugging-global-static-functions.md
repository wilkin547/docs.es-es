---
description: 'Más información sobre: depurar funciones estáticas globales'
title: Funciones estáticas globales para la depuración
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
ms.openlocfilehash: efee1bfb6eb61ae2311320a4c12bf08ec0f9534b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661459"
---
# <a name="debugging-global-static-functions"></a><span data-ttu-id="5af58-103">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="5af58-103">Debugging Global Static Functions</span></span>

<span data-ttu-id="5af58-104">Esta sección describe las funciones estáticas globales no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="5af58-104">This section describes the unmanaged global static functions that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5af58-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5af58-105">In This Section</span></span>  

 [<span data-ttu-id="5af58-106">_EFN_GetManagedExcepStack (Función)</span><span class="sxs-lookup"><span data-stu-id="5af58-106">_EFN_GetManagedExcepStack Function</span></span>](efn-getmanagedexcepstack-function.md)  
 <span data-ttu-id="5af58-107">Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.</span><span class="sxs-lookup"><span data-stu-id="5af58-107">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
 [<span data-ttu-id="5af58-108">_EFN_GetManagedObjectFieldInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="5af58-108">_EFN_GetManagedObjectFieldInfo Function</span></span>](efn-getmanagedobjectfieldinfo-function.md)  
 <span data-ttu-id="5af58-109">Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.</span><span class="sxs-lookup"><span data-stu-id="5af58-109">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
 [<span data-ttu-id="5af58-110">_EFN_GetManagedObjectName (Función)</span><span class="sxs-lookup"><span data-stu-id="5af58-110">_EFN_GetManagedObjectName Function</span></span>](efn-getmanagedobjectname-function.md)  
 <span data-ttu-id="5af58-111">Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.</span><span class="sxs-lookup"><span data-stu-id="5af58-111">Gets the name of a type by using the provided managed object pointer.</span></span>  
  
 [<span data-ttu-id="5af58-112">_EFN_StackTrace (Función)</span><span class="sxs-lookup"><span data-stu-id="5af58-112">_EFN_StackTrace Function</span></span>](efn-stacktrace-function.md)  
 <span data-ttu-id="5af58-113">Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.</span><span class="sxs-lookup"><span data-stu-id="5af58-113">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
 [<span data-ttu-id="5af58-114">CLRDataCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="5af58-114">CLRDataCreateInstance Function</span></span>](clrdatacreateinstance-function.md)  
 <span data-ttu-id="5af58-115">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para crear el objeto de interfaz especificado para el proceso de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="5af58-115">Called by the common language runtime (CLR) data access services to create the specified interface object for the specified target process.</span></span>  
  
 [<span data-ttu-id="5af58-116">puntero a la función PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="5af58-116">PFN_CLRDataCreateInstance Function Pointer</span></span>](pfn-clrdatacreateinstance-function-pointer.md)  
 <span data-ttu-id="5af58-117">Señala una función a la que llaman los servicios de acceso a datos de CLR para crear el objeto de interfaz especificado para el proceso de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="5af58-117">Points to a function that is called by the CLR data access services to create the specified interface object for the specified target process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5af58-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5af58-118">Related Sections</span></span>  

 [<span data-ttu-id="5af58-119">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="5af58-119">Debugging Coclasses</span></span>](debugging-coclasses.md)  
  
 [<span data-ttu-id="5af58-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5af58-120">Debugging Interfaces</span></span>](debugging-interfaces.md)  
  
 [<span data-ttu-id="5af58-121">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="5af58-121">Debugging Enumerations</span></span>](debugging-enumerations.md)  
  
 [<span data-ttu-id="5af58-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="5af58-122">Debugging Structures</span></span>](debugging-structures.md)
