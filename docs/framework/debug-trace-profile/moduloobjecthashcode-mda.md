---
title: MDA de moduloObjectHashcode
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d8f6975d117d9920d2199c3996246822d1fdb6c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170786"
---
# <a name="moduloobjecthashcode-mda"></a><span data-ttu-id="3044e-102">MDA de moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="3044e-102">moduloObjectHashcode MDA</span></span>
<span data-ttu-id="3044e-103">El Asistente para la depuración administrada (MDA) `moduloObjectHashcode` cambia el comportamiento de la clase <xref:System.Object> para realizar una operación de módulo en el código hash devuelto por el método <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="3044e-103">The `moduloObjectHashcode` managed debugging assistant (MDA) changes the behavior of the <xref:System.Object> class to perform a modulo operation on the hash code returned by the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="3044e-104">El módulo predeterminado para este MDA es 1, lo que hace que <xref:System.Object.GetHashCode%2A> devuelva 0 para todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="3044e-104">The default modulus for this MDA is 1, which causes <xref:System.Object.GetHashCode%2A> to return 0 for all objects.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3044e-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="3044e-105">Symptoms</span></span>  
 <span data-ttu-id="3044e-106">Después de moverlo a una nueva versión de Common Language Runtime (CLR), un programa ya no se ejecuta correctamente:</span><span class="sxs-lookup"><span data-stu-id="3044e-106">After moving to a new version of the common language runtime (CLR), a program no longer executes properly:</span></span>  
  
-   <span data-ttu-id="3044e-107">El programa está recibiendo el objeto equivocado desde una <xref:System.Collections.Hashtable>.</span><span class="sxs-lookup"><span data-stu-id="3044e-107">The program is getting the wrong object from a <xref:System.Collections.Hashtable>.</span></span>  
  
-   <span data-ttu-id="3044e-108">El orden de enumeración de una <xref:System.Collections.Hashtable> tiene un cambio que interrumpe el programa.</span><span class="sxs-lookup"><span data-stu-id="3044e-108">The order of enumeration from a <xref:System.Collections.Hashtable> has a change that breaks the program.</span></span>  
  
-   <span data-ttu-id="3044e-109">Dos objetos que solían ser iguales ya no lo son.</span><span class="sxs-lookup"><span data-stu-id="3044e-109">Two objects that used to be equal are no longer equal.</span></span>  
  
-   <span data-ttu-id="3044e-110">Dos objetos que solían ser no iguales ahora lo son.</span><span class="sxs-lookup"><span data-stu-id="3044e-110">Two objects that used to not be equal are now equal.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3044e-111">Motivo</span><span class="sxs-lookup"><span data-stu-id="3044e-111">Cause</span></span>  
 <span data-ttu-id="3044e-112">El programa puede estar recibiendo el objeto equivocado desde <xref:System.Collections.Hashtable> porque la implementación del método <xref:System.Object.Equals%2A> en la clase para la clave en <xref:System.Collections.Hashtable> comprueba la igualdad de objetos al comparar los resultados de la llamada al método <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="3044e-112">Your program may be getting the wrong object from a <xref:System.Collections.Hashtable> because the implementation of the <xref:System.Object.Equals%2A> method on the class for the key into the <xref:System.Collections.Hashtable> tests for equality of objects by comparing the results of the call to the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="3044e-113">No deben usarse códigos hash para comprobar la igualdad de objetos porque dos objetos pueden tener el mismo código hash incluso si sus respectivos campos tienen valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="3044e-113">Hash codes should not be used to test for object equality because two objects may have the same hash code even if their respective fields have different values.</span></span> <span data-ttu-id="3044e-114">Estas colisiones de código hash, aunque sean poco frecuentes en la práctica, se producen.</span><span class="sxs-lookup"><span data-stu-id="3044e-114">These hash code collisions, although rare in practice, do occur.</span></span> <span data-ttu-id="3044e-115">El efecto que tiene en una búsqueda de <xref:System.Collections.Hashtable> es que dos claves que no son iguales parecen iguales, y se devuelve el objeto incorrecto de la <xref:System.Collections.Hashtable>.</span><span class="sxs-lookup"><span data-stu-id="3044e-115">The effect this has on a <xref:System.Collections.Hashtable> lookup is that two keys which are not equal appear to be equal, and the wrong object is returned from the <xref:System.Collections.Hashtable>.</span></span> <span data-ttu-id="3044e-116">Por motivos de rendimiento, la implementación de <xref:System.Object.GetHashCode%2A> puede cambiar entre las versiones del tiempo de ejecución, por lo que es posible que en una versión se produzcan conflictos que no aparezcan en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3044e-116">For performance reasons, the implementation of <xref:System.Object.GetHashCode%2A> can change between runtime versions, so collisions that might not occur on one version might occur on subsequent versions.</span></span> <span data-ttu-id="3044e-117">Habilite este MDA para probar si el código tiene errores cuando se producen colisiones de códigos hash.</span><span class="sxs-lookup"><span data-stu-id="3044e-117">Enable this MDA to test whether your code has bugs when hash codes collide.</span></span> <span data-ttu-id="3044e-118">Cuando está habilitado, este MDA hace que el método <xref:System.Object.GetHashCode%2A> devuelva un valor 0, lo que provoca que todos los códigos hash colisionen.</span><span class="sxs-lookup"><span data-stu-id="3044e-118">When enabled, this MDA causes the <xref:System.Object.GetHashCode%2A> method to return 0, resulting in all hash codes colliding.</span></span> <span data-ttu-id="3044e-119">El único efecto que debería tener la habilitación de este MDA en el programa es que se ejecute más lentamente.</span><span class="sxs-lookup"><span data-stu-id="3044e-119">The only effect enabling this MDA should have on your program is that your program runs slower.</span></span>  
  
 <span data-ttu-id="3044e-120">El orden de enumeración de una <xref:System.Collections.Hashtable> puede cambiar de una versión del tiempo de ejecución a otra si cambia el algoritmo que se usa para calcular los códigos hash para la clave.</span><span class="sxs-lookup"><span data-stu-id="3044e-120">The order of enumeration from a <xref:System.Collections.Hashtable> may change from one version of the runtime to another if the algorithm used to compute the hash codes for the key change.</span></span> <span data-ttu-id="3044e-121">Para comprobar si el programa ha tomado una dependencia en el orden de enumeración de claves o valores fuera de una tabla hash, puede habilitar este MDA.</span><span class="sxs-lookup"><span data-stu-id="3044e-121">To test whether your program has taken a dependency on the order of enumeration of keys or values out of a hash table, you can enable this MDA.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3044e-122">Resolución</span><span class="sxs-lookup"><span data-stu-id="3044e-122">Resolution</span></span>  
 <span data-ttu-id="3044e-123">Nunca use códigos hash como sustitutos de la identidad de objetos.</span><span class="sxs-lookup"><span data-stu-id="3044e-123">Never use hash codes as a substitute for object identity.</span></span> <span data-ttu-id="3044e-124">Implemente la invalidación del método <xref:System.Object.Equals%2A?displayProperty=nameWithType> para no comparar códigos hash.</span><span class="sxs-lookup"><span data-stu-id="3044e-124">Implement the override of the <xref:System.Object.Equals%2A?displayProperty=nameWithType> method to not compare hash codes.</span></span>  
  
 <span data-ttu-id="3044e-125">No cree dependencias en el orden de las enumeraciones de claves o valores en tablas hash.</span><span class="sxs-lookup"><span data-stu-id="3044e-125">Do not create dependencies on the order of enumerations of keys or values in hash tables.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3044e-126">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="3044e-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="3044e-127">Las aplicaciones se ejecutan más despacio cuando se habilita este MDA.</span><span class="sxs-lookup"><span data-stu-id="3044e-127">Applications run more slowly when this MDA is enabled.</span></span> <span data-ttu-id="3044e-128">Este MDA simplemente toma el código hash que se habría devuelto y, en su lugar, devuelve el resto cuando se divide por un módulo.</span><span class="sxs-lookup"><span data-stu-id="3044e-128">This MDA simply takes the hash code that would have been returned and instead returns the remainder when divided by a modulus.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3044e-129">Salida</span><span class="sxs-lookup"><span data-stu-id="3044e-129">Output</span></span>  
 <span data-ttu-id="3044e-130">No hay ningún resultado para este MDA.</span><span class="sxs-lookup"><span data-stu-id="3044e-130">There is no output for this MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3044e-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="3044e-131">Configuration</span></span>  
 <span data-ttu-id="3044e-132">El atributo `modulus` especifica el módulo que se usa en el código hash.</span><span class="sxs-lookup"><span data-stu-id="3044e-132">The `modulus` attribute specifies the modulus used on the hash code.</span></span> <span data-ttu-id="3044e-133">El valor predeterminado es 1.</span><span class="sxs-lookup"><span data-stu-id="3044e-133">The default value is 1.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3044e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3044e-134">See also</span></span>

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3044e-135">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="3044e-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
