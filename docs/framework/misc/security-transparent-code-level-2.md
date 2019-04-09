---
title: Código transparente en seguridad, nivel 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62c25b14fa7b3867bbdbcb2f1e08cc16ce349e72
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156083"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="22491-102">Código transparente en seguridad, nivel 2</span><span class="sxs-lookup"><span data-stu-id="22491-102">Security-Transparent Code, Level 2</span></span>
<a name="top"></a>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="22491-103">La transparencia de nivel 2 se introdujo en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22491-103">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="22491-104">Los tres principios de este modelo son código transparente, código crítico para la seguridad y disponible desde código transparente, y código crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22491-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>  
  
-   <span data-ttu-id="22491-105">El código transparente, incluido el código que se ejecuta como de plena confianza, solo puede llamar a otro código transparente o a código crítico para la seguridad y disponible desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="22491-106">Solo puede realizar acciones permitidas por el conjunto de permisos de confianza parcial del dominio (si existe).</span><span class="sxs-lookup"><span data-stu-id="22491-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="22491-107">El código transparente no puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22491-107">Transparent code cannot do the following:</span></span>  
  
    -   <span data-ttu-id="22491-108">Realizar una instrucción <xref:System.Security.CodeAccessPermission.Assert%2A> o una elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="22491-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>  
  
    -   <span data-ttu-id="22491-109">Contener código no seguro o no comprobable.</span><span class="sxs-lookup"><span data-stu-id="22491-109">Contain unsafe or unverifiable code.</span></span>  
  
    -   <span data-ttu-id="22491-110">Llamar directamente a código crítico.</span><span class="sxs-lookup"><span data-stu-id="22491-110">Directly call critical code.</span></span>  
  
    -   <span data-ttu-id="22491-111">Llamar a código nativo o código con el atributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.</span><span class="sxs-lookup"><span data-stu-id="22491-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>  
  
    -   <span data-ttu-id="22491-112">Llamar a un miembro que está protegido por <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span><span class="sxs-lookup"><span data-stu-id="22491-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>  
  
    -   <span data-ttu-id="22491-113">Heredar de tipos críticos.</span><span class="sxs-lookup"><span data-stu-id="22491-113">Inherit from critical types.</span></span>  
  
     <span data-ttu-id="22491-114">Además, los métodos transparentes no pueden invalidar métodos virtuales críticos o implementar métodos de interfaz críticos.</span><span class="sxs-lookup"><span data-stu-id="22491-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>  
  
-   <span data-ttu-id="22491-115">El código crítico para la seguridad es de plena confianza, pero el código transparente puede llamarlo.</span><span class="sxs-lookup"><span data-stu-id="22491-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="22491-116">Expone un área expuesta limitada de código de plena confianza; las comprobaciones de corrección y seguridad se producen en código crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22491-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>  
  
-   <span data-ttu-id="22491-117">El código crítico para la seguridad puede llamar a cualquier código y es de plena confianza, pero no se puede llamar mediante código transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>  
  
 <span data-ttu-id="22491-118">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="22491-118">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="22491-119">Ejemplos de uso y comportamientos</span><span class="sxs-lookup"><span data-stu-id="22491-119">Usage Examples and Behaviors</span></span>](#examples)  
  
-   [<span data-ttu-id="22491-120">Patrones de invalidación</span><span class="sxs-lookup"><span data-stu-id="22491-120">Override Patterns</span></span>](#override)  
  
-   [<span data-ttu-id="22491-121">Reglas de herencia</span><span class="sxs-lookup"><span data-stu-id="22491-121">Inheritance Rules</span></span>](#inheritance)  
  
-   [<span data-ttu-id="22491-122">Información y reglas adicionales</span><span class="sxs-lookup"><span data-stu-id="22491-122">Additional Information and Rules</span></span>](#additional)  
  
<a name="examples"></a>   
## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="22491-123">Ejemplos de uso y comportamientos</span><span class="sxs-lookup"><span data-stu-id="22491-123">Usage Examples and Behaviors</span></span>  
 <span data-ttu-id="22491-124">Para especificar reglas de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] (transparencia de nivel 2), use la siguiente anotación para un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="22491-124">To specify [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules (level 2 transparency), use the following annotation for an assembly:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 <span data-ttu-id="22491-125">Para bloquear en las reglas de .NET Framework 2.0 (transparencia de nivel 1), use la siguiente anotación:</span><span class="sxs-lookup"><span data-stu-id="22491-125">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 <span data-ttu-id="22491-126">Si no anota un ensamblado, se usan las reglas de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22491-126">If you do not annotate an assembly, the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules are used by default.</span></span> <span data-ttu-id="22491-127">Sin embargo, la práctica recomendada es usar el <xref:System.Security.SecurityRulesAttribute> en lugar del atributo según el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="22491-127">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>  
  
### <a name="assembly-wide-annotation"></a><span data-ttu-id="22491-128">Anotación de todo el ensamblado</span><span class="sxs-lookup"><span data-stu-id="22491-128">Assembly-wide Annotation</span></span>  
 <span data-ttu-id="22491-129">Las reglas siguientes se aplican al uso de atributos en el nivel de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="22491-129">The following rules apply to the use of attributes at the assembly level:</span></span>  
  
-   <span data-ttu-id="22491-130">No hay atributos: Si no especifica ningún atributo, el tiempo de ejecución interpreta todo el código como crítico para la seguridad, excepto cuando es crítico para la seguridad infringen una regla de herencia (por ejemplo, al invalidar o implementar un modo transparente el método de interfaz o virtual).</span><span class="sxs-lookup"><span data-stu-id="22491-130">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="22491-131">En esos casos, los métodos son críticos para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22491-131">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="22491-132">Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="22491-132">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>  
  
-   `SecurityTransparent`<span data-ttu-id="22491-133">: Todo el código es transparente; el ensamblado completo no hará nada con privilegios o unsafe.</span><span class="sxs-lookup"><span data-stu-id="22491-133">: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>  
  
-   `SecurityCritical`<span data-ttu-id="22491-134">: Todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-134">: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="22491-135">Este escenario se parece a cuando no se especifica ningún atributo; sin embargo, Common Language Runtime no determina automáticamente las reglas de transparencia.</span><span class="sxs-lookup"><span data-stu-id="22491-135">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="22491-136">Por ejemplo, si invalida un método virtual o abstracto o si implementa un método de interfaz, de forma predeterminada, ese método es transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-136">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="22491-137">Debe anotar explícitamente el método como `SecurityCritical` o `SecuritySafeCritical`; de lo contrario, se producirá una <xref:System.TypeLoadException> en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="22491-137">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="22491-138">Esta regla también se aplica cuando la clase base y la clase derivada están en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="22491-138">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>  
  
-   `AllowPartiallyTrustedCallers` <span data-ttu-id="22491-139">(nivel 2 solo): El valor predeterminado de todo el código es transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-139">(level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="22491-140">Sin embargo, los miembros y tipos individuales pueden tener otros atributos.</span><span class="sxs-lookup"><span data-stu-id="22491-140">However, individual types and members can have other attributes.</span></span>  
  
 <span data-ttu-id="22491-141">En la tabla siguiente compara el comportamiento de nivel de ensamblado de nivel 2 y nivel 1.</span><span class="sxs-lookup"><span data-stu-id="22491-141">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>  
  
|<span data-ttu-id="22491-142">Assembly (atributo)</span><span class="sxs-lookup"><span data-stu-id="22491-142">Assembly attribute</span></span>|<span data-ttu-id="22491-143">Nivel 2</span><span class="sxs-lookup"><span data-stu-id="22491-143">Level 2</span></span>|<span data-ttu-id="22491-144">nivel 1</span><span class="sxs-lookup"><span data-stu-id="22491-144">Level 1</span></span>|  
|------------------------|-------------|-------------|  
|<span data-ttu-id="22491-145">Ningún atributo en un ensamblado de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="22491-145">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="22491-146">Los tipos y los miembros son transparentes de forma predeterminada, pero pueden ser críticos para la seguridad o bien críticos para la seguridad y disponibles desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-146">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="22491-147">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="22491-147">All types and members are transparent.</span></span>|  
|<span data-ttu-id="22491-148">Ningún atributo</span><span class="sxs-lookup"><span data-stu-id="22491-148">No attribute</span></span>|<span data-ttu-id="22491-149">Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="22491-149">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="22491-150">Todos los tipos y los miembros son críticos para la seguridad, excepto cuando el hecho de ser críticos para la seguridad infringe una regla de herencia.</span><span class="sxs-lookup"><span data-stu-id="22491-150">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="22491-151">En un ensamblado de plena confianza (en la caché global de ensamblados, o identificado como de plena confianza en `AppDomain`), todos los tipos son transparentes y todos los miembros son críticos para la seguridad y disponibles desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-151">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|  
|`SecurityTransparent`|<span data-ttu-id="22491-152">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="22491-152">All types and members are transparent.</span></span>|<span data-ttu-id="22491-153">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="22491-153">All types and members are transparent.</span></span>|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="22491-154">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="22491-154">Not applicable.</span></span>|<span data-ttu-id="22491-155">Todos los tipos y los miembros son críticos para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22491-155">All types and members are security-critical.</span></span>|  
|`SecurityCritical`|<span data-ttu-id="22491-156">Todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-156">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="22491-157">Si invalida un método virtual o abstracto o si implementa un método de interfaz, debe anotar explícitamente ese método como `SecurityCritical` o `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="22491-157">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="22491-158">El valor predeterminado de todo el código es transparente.</span><span class="sxs-lookup"><span data-stu-id="22491-158">All code defaults to transparent.</span></span> <span data-ttu-id="22491-159">Sin embargo, los miembros y tipos individuales pueden tener otros atributos.</span><span class="sxs-lookup"><span data-stu-id="22491-159">However, individual types and members can have other attributes.</span></span>|  
  
### <a name="type-and-member-annotation"></a><span data-ttu-id="22491-160">Anotación de tipos y de miembros</span><span class="sxs-lookup"><span data-stu-id="22491-160">Type and Member Annotation</span></span>  
 <span data-ttu-id="22491-161">Los atributos de seguridad que se aplican a un tipo también se aplican a los miembros que el tipo introduce.</span><span class="sxs-lookup"><span data-stu-id="22491-161">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="22491-162">Sin embargo, no se aplican a invalidaciones virtuales o abstractas de la clase base o implementaciones de interfaz.</span><span class="sxs-lookup"><span data-stu-id="22491-162">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="22491-163">Las reglas siguientes se aplican al uso de atributos en el nivel de tipo y miembro:</span><span class="sxs-lookup"><span data-stu-id="22491-163">The following rules apply to the use of attributes at the type and member level:</span></span>  
  
-   `SecurityCritical`<span data-ttu-id="22491-164">: El tipo o miembro es crítico y se puede llamar a solamente el código de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="22491-164">: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="22491-165">Los métodos que se introducen en un tipo crítico para la seguridad son críticos.</span><span class="sxs-lookup"><span data-stu-id="22491-165">Methods that are introduced in a security-critical type are critical.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="22491-166">Los métodos abstractos y virtuales que se introducen en interfaces o clases base y que se invalidan o se implementan en una clase crítica para la seguridad son transparentes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22491-166">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="22491-167">Se deben identificar como `SecuritySafeCritical` o `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="22491-167">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>  
  
-   `SecuritySafeCritical`<span data-ttu-id="22491-168">: El tipo o miembro es crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22491-168">: The type or member is safe-critical.</span></span> <span data-ttu-id="22491-169">Sin embargo, puede llamarse al tipo o miembro desde código transparente (de confianza parcial) y es tan capaz como cualquier otro código crítico.</span><span class="sxs-lookup"><span data-stu-id="22491-169">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="22491-170">El código se debe auditar para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22491-170">The code must be audited for security.</span></span>  
  
 [<span data-ttu-id="22491-171">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="22491-171">Back to top</span></span>](#top)  
  
<a name="override"></a>   
## <a name="override-patterns"></a><span data-ttu-id="22491-172">Patrones de invalidación</span><span class="sxs-lookup"><span data-stu-id="22491-172">Override Patterns</span></span>  
 <span data-ttu-id="22491-173">La siguiente tabla muestra las invalidaciones de método permitidas para la transparencia de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="22491-173">The following table shows the method overrides allowed for level 2 transparency.</span></span>  
  
|<span data-ttu-id="22491-174">Miembro base virtual/de interfaz</span><span class="sxs-lookup"><span data-stu-id="22491-174">Base virtual/interface member</span></span>|<span data-ttu-id="22491-175">Invalidación/interfaz</span><span class="sxs-lookup"><span data-stu-id="22491-175">Override/interface</span></span>|  
|------------------------------------|-------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [<span data-ttu-id="22491-176">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="22491-176">Back to top</span></span>](#top)  
  
<a name="inheritance"></a>   
## <a name="inheritance-rules"></a><span data-ttu-id="22491-177">Reglas de herencia</span><span class="sxs-lookup"><span data-stu-id="22491-177">Inheritance Rules</span></span>  
 <span data-ttu-id="22491-178">En esta sección, se asigna el siguiente orden a código `Transparent`, `Critical` y `SafeCritical` en función del acceso y las capacidades:</span><span class="sxs-lookup"><span data-stu-id="22491-178">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>  
  
 `Transparent` < `SafeCritical` < `Critical`  
  
-   <span data-ttu-id="22491-179">Reglas para tipos: Va de izquierda a derecha, el acceso se vuelve más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="22491-179">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="22491-180">Los tipos derivados deben ser al menos tan restrictivos como el tipo base.</span><span class="sxs-lookup"><span data-stu-id="22491-180">Derived types must be at least as restrictive as the base type.</span></span>  
  
-   <span data-ttu-id="22491-181">Reglas para métodos: Los métodos derivados no pueden cambiar la accesibilidad del método base.</span><span class="sxs-lookup"><span data-stu-id="22491-181">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="22491-182">Para el comportamiento predeterminado, todos los métodos derivados no anotados son `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="22491-182">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="22491-183">Los derivados de tipos críticos provocan una excepción que se produce si el método invalidado no está anotado explícitamente como `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="22491-183">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>  
  
 <span data-ttu-id="22491-184">En la tabla siguiente se muestran los patrones de herencia de tipo permitidos.</span><span class="sxs-lookup"><span data-stu-id="22491-184">The following table shows the allowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="22491-185">Clase base</span><span class="sxs-lookup"><span data-stu-id="22491-185">Base class</span></span>|<span data-ttu-id="22491-186">La clase derivada puede ser</span><span class="sxs-lookup"><span data-stu-id="22491-186">Derived class can be</span></span>|  
|----------------|--------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="22491-187">En la tabla siguiente se muestran los patrones de herencia de tipo no permitidos.</span><span class="sxs-lookup"><span data-stu-id="22491-187">The following table shows the disallowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="22491-188">Clase base</span><span class="sxs-lookup"><span data-stu-id="22491-188">Base class</span></span>|<span data-ttu-id="22491-189">La clase derivada no puede ser</span><span class="sxs-lookup"><span data-stu-id="22491-189">Derived class cannot be</span></span>|  
|----------------|-----------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 <span data-ttu-id="22491-190">En la tabla siguiente se muestran los patrones de herencia de método permitidos.</span><span class="sxs-lookup"><span data-stu-id="22491-190">The following table shows the allowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="22491-191">Método base</span><span class="sxs-lookup"><span data-stu-id="22491-191">Base method</span></span>|<span data-ttu-id="22491-192">El método derivado puede ser</span><span class="sxs-lookup"><span data-stu-id="22491-192">Derived method can be</span></span>|  
|-----------------|---------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="22491-193">En la tabla siguiente se muestran los patrones de herencia de método no permitidos.</span><span class="sxs-lookup"><span data-stu-id="22491-193">The following table shows the disallowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="22491-194">Método base</span><span class="sxs-lookup"><span data-stu-id="22491-194">Base method</span></span>|<span data-ttu-id="22491-195">El método derivado no puede ser</span><span class="sxs-lookup"><span data-stu-id="22491-195">Derived method cannot be</span></span>|  
|-----------------|------------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  <span data-ttu-id="22491-196">Estas reglas de herencia se aplican a los tipos y miembros de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="22491-196">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="22491-197">Los tipos de ensamblados de nivel 1 pueden heredar de tipos y miembros críticos para la seguridad de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="22491-197">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="22491-198">Por lo tanto, los tipos y miembros de nivel 2 deben tener peticiones de herencia independientes para los herederos de nivel 1.</span><span class="sxs-lookup"><span data-stu-id="22491-198">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>  
  
 [<span data-ttu-id="22491-199">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="22491-199">Back to top</span></span>](#top)  
  
<a name="additional"></a>   
## <a name="additional-information-and-rules"></a><span data-ttu-id="22491-200">Información y reglas adicionales</span><span class="sxs-lookup"><span data-stu-id="22491-200">Additional Information and Rules</span></span>  
  
### <a name="linkdemand-support"></a><span data-ttu-id="22491-201">Compatibilidad con LinkDemand</span><span class="sxs-lookup"><span data-stu-id="22491-201">LinkDemand Support</span></span>  
 <span data-ttu-id="22491-202">El modelo de transparencia de nivel 2 reemplaza <xref:System.Security.Permissions.SecurityAction.LinkDemand> con el atributo <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="22491-202">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="22491-203">En código heredado (nivel 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> se trata automáticamente como <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="22491-203">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>  
  
### <a name="reflection"></a><span data-ttu-id="22491-204">Reflexión</span><span class="sxs-lookup"><span data-stu-id="22491-204">Reflection</span></span>  
 <span data-ttu-id="22491-205">El hecho de invocar un método crítico o leer un campo crítico desencadena una petición de plena confianza (como si se estuviera invocando un método o campo privados).</span><span class="sxs-lookup"><span data-stu-id="22491-205">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="22491-206">Por lo tanto, el código de plena confianza puede invocar un método crítico, mientras que el código de confianza parcial no puede.</span><span class="sxs-lookup"><span data-stu-id="22491-206">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>  
  
 <span data-ttu-id="22491-207">Se han agregado las siguientes propiedades al espacio de nombres <xref:System.Reflection> para determinar si el tipo, método o campo es `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> y <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="22491-207">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="22491-208">Use estas propiedades para determinar la transparencia mediante la reflexión en lugar de comprobar la presencia del atributo.</span><span class="sxs-lookup"><span data-stu-id="22491-208">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="22491-209">Las reglas de transparencia son complejas y la comprobación del atributo podría no ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="22491-209">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22491-210">Un `SafeCritical` devuelve del método `true` para ambos <xref:System.Type.IsSecurityCritical%2A> y <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, porque `SafeCritical` es crítico (tiene las mismas funcionalidades que el código crítico, pero se puede llamar desde código transparente).</span><span class="sxs-lookup"><span data-stu-id="22491-210">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>  
  
 <span data-ttu-id="22491-211">Los métodos dinámicos heredan la transparencia de los módulos a los que se adjuntan; no heredan la transparencia del tipo (si están conectados a un tipo).</span><span class="sxs-lookup"><span data-stu-id="22491-211">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>  
  
### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="22491-212">Omitir la comprobación en plena confianza</span><span class="sxs-lookup"><span data-stu-id="22491-212">Skip Verification in Full Trust</span></span>  
 <span data-ttu-id="22491-213">Puede omitir la comprobación para ensamblados transparentes de plena confianza estableciendo la propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> en `true` en el atributo <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="22491-213">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 <span data-ttu-id="22491-214">La propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> es `false` de forma predeterminada, por lo que la propiedad debe establecerse en `true` para omitir la comprobación.</span><span class="sxs-lookup"><span data-stu-id="22491-214">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="22491-215">Esto debe hacerse únicamente con fines de optimización.</span><span class="sxs-lookup"><span data-stu-id="22491-215">This should be done for optimization purposes only.</span></span> <span data-ttu-id="22491-216">Debe asegurarse de que el código transparente en el ensamblado sea comprobable usando la `transparent` opción el [herramienta PEVerify](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="22491-216">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22491-217">Vea también</span><span class="sxs-lookup"><span data-stu-id="22491-217">See also</span></span>

- [<span data-ttu-id="22491-218">Código transparente en seguridad, nivel 1</span><span class="sxs-lookup"><span data-stu-id="22491-218">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [<span data-ttu-id="22491-219">Cambios de seguridad</span><span class="sxs-lookup"><span data-stu-id="22491-219">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
