---
title: Código transparente en seguridad, nivel 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: 12e991e4977b0866343158c05681ddf4bd0c869b
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645733"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="0e534-102">Código transparente en seguridad, nivel 2</span><span class="sxs-lookup"><span data-stu-id="0e534-102">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="0e534-103">La transparencia de nivel 2 se introdujo en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0e534-103">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="0e534-104">Los tres principios de este modelo son código transparente, código crítico para la seguridad y disponible desde código transparente, y código crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e534-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="0e534-105">El código transparente, incluido el código que se ejecuta como de plena confianza, solo puede llamar a otro código transparente o a código crítico para la seguridad y disponible desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="0e534-106">Solo puede realizar acciones permitidas por el conjunto de permisos de confianza parcial del dominio (si existe).</span><span class="sxs-lookup"><span data-stu-id="0e534-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="0e534-107">El código transparente no puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e534-107">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="0e534-108">Realizar una instrucción <xref:System.Security.CodeAccessPermission.Assert%2A> o una elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="0e534-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="0e534-109">Contener código no seguro o no comprobable.</span><span class="sxs-lookup"><span data-stu-id="0e534-109">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="0e534-110">Llamar directamente a código crítico.</span><span class="sxs-lookup"><span data-stu-id="0e534-110">Directly call critical code.</span></span>

  - <span data-ttu-id="0e534-111">Llamar a código nativo o código con el atributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0e534-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="0e534-112">Llamar a un miembro que está protegido por <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span><span class="sxs-lookup"><span data-stu-id="0e534-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="0e534-113">Heredar de tipos críticos.</span><span class="sxs-lookup"><span data-stu-id="0e534-113">Inherit from critical types.</span></span>

  <span data-ttu-id="0e534-114">Además, los métodos transparentes no pueden invalidar métodos virtuales críticos o implementar métodos de interfaz críticos.</span><span class="sxs-lookup"><span data-stu-id="0e534-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="0e534-115">El código crítico para la seguridad es de plena confianza, pero el código transparente puede llamarlo.</span><span class="sxs-lookup"><span data-stu-id="0e534-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="0e534-116">Expone un área expuesta limitada de código de plena confianza; las comprobaciones de corrección y seguridad se producen en código crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e534-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="0e534-117">El código crítico para la seguridad puede llamar a cualquier código y es de plena confianza, pero no se puede llamar mediante código transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="0e534-118">Ejemplos de uso y comportamientos</span><span class="sxs-lookup"><span data-stu-id="0e534-118">Usage Examples and Behaviors</span></span>

<span data-ttu-id="0e534-119">Para especificar reglas de .NET Framework 4 (transparencia de nivel 2), utilice la anotación siguiente para un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="0e534-119">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="0e534-120">Para bloquear en las reglas de .NET Framework 2.0 (transparencia de nivel 1), use la siguiente anotación:</span><span class="sxs-lookup"><span data-stu-id="0e534-120">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="0e534-121">Si no anota un ensamblado, las reglas de .NET Framework 4 se usan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e534-121">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="0e534-122">Sin embargo, el procedimiento <xref:System.Security.SecurityRulesAttribute> recomendado es usar el atributo en lugar de depender del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0e534-122">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="0e534-123">Anotación de todo el ensamblado</span><span class="sxs-lookup"><span data-stu-id="0e534-123">Assembly-wide Annotation</span></span>

<span data-ttu-id="0e534-124">Las reglas siguientes se aplican al uso de atributos en el nivel de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="0e534-124">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="0e534-125">Ningún atributo: si no se especifica ningún atributo, el tiempo de ejecución interpreta todo el código como crítico para la seguridad, excepto cuando por el hecho de ser crítico para la seguridad infringe una regla de herencia (por ejemplo, al invalidar o implementar un método de interfaz o virtual transparente).</span><span class="sxs-lookup"><span data-stu-id="0e534-125">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="0e534-126">En esos casos, los métodos son críticos para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e534-126">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="0e534-127">Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0e534-127">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="0e534-128">`SecurityTransparent`: todo el código es transparente; el ensamblado completo no hará nada que tenga privilegios o no sea seguro.</span><span class="sxs-lookup"><span data-stu-id="0e534-128">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="0e534-129">`SecurityCritical`: todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-129">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="0e534-130">Este escenario se parece a cuando no se especifica ningún atributo; sin embargo, Common Language Runtime no determina automáticamente las reglas de transparencia.</span><span class="sxs-lookup"><span data-stu-id="0e534-130">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="0e534-131">Por ejemplo, si invalida un método virtual o abstracto o si implementa un método de interfaz, de forma predeterminada, ese método es transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-131">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="0e534-132">Debe anotar explícitamente el método como `SecurityCritical` o `SecuritySafeCritical`; de lo contrario, se producirá una <xref:System.TypeLoadException> en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="0e534-132">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="0e534-133">Esta regla también se aplica cuando la clase base y la clase derivada están en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0e534-133">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="0e534-134">`AllowPartiallyTrustedCallers` (solo nivel 2): el valor predeterminado de todo el código es transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-134">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="0e534-135">Sin embargo, los miembros y tipos individuales pueden tener otros atributos.</span><span class="sxs-lookup"><span data-stu-id="0e534-135">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="0e534-136">En la tabla siguiente se compara el comportamiento del nivel de ensamblado para el nivel 2 con el nivel 1.</span><span class="sxs-lookup"><span data-stu-id="0e534-136">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="0e534-137">Atributo de ensamblado</span><span class="sxs-lookup"><span data-stu-id="0e534-137">Assembly attribute</span></span>|<span data-ttu-id="0e534-138">Nivel 2</span><span class="sxs-lookup"><span data-stu-id="0e534-138">Level 2</span></span>|<span data-ttu-id="0e534-139">Nivel 1</span><span class="sxs-lookup"><span data-stu-id="0e534-139">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="0e534-140">Ningún atributo en un ensamblado de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="0e534-140">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="0e534-141">Los tipos y los miembros son transparentes de forma predeterminada, pero pueden ser críticos para la seguridad o bien críticos para la seguridad y disponibles desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-141">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="0e534-142">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="0e534-142">All types and members are transparent.</span></span>|
|<span data-ttu-id="0e534-143">Ningún atributo</span><span class="sxs-lookup"><span data-stu-id="0e534-143">No attribute</span></span>|<span data-ttu-id="0e534-144">Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0e534-144">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="0e534-145">Todos los tipos y los miembros son críticos para la seguridad, excepto cuando el hecho de ser críticos para la seguridad infringe una regla de herencia.</span><span class="sxs-lookup"><span data-stu-id="0e534-145">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="0e534-146">En un ensamblado de plena confianza (en la caché global de ensamblados, o identificado como de plena confianza en `AppDomain`), todos los tipos son transparentes y todos los miembros son críticos para la seguridad y disponibles desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-146">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="0e534-147">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="0e534-147">All types and members are transparent.</span></span>|<span data-ttu-id="0e534-148">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="0e534-148">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="0e534-149">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="0e534-149">Not applicable.</span></span>|<span data-ttu-id="0e534-150">Todos los tipos y los miembros son críticos para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e534-150">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="0e534-151">Todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-151">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="0e534-152">Si invalida un método virtual o abstracto o si implementa un método de interfaz, debe anotar explícitamente ese método como `SecurityCritical` o `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="0e534-152">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="0e534-153">El valor predeterminado de todo el código es transparente.</span><span class="sxs-lookup"><span data-stu-id="0e534-153">All code defaults to transparent.</span></span> <span data-ttu-id="0e534-154">Sin embargo, los miembros y tipos individuales pueden tener otros atributos.</span><span class="sxs-lookup"><span data-stu-id="0e534-154">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="0e534-155">Anotación de tipos y de miembros</span><span class="sxs-lookup"><span data-stu-id="0e534-155">Type and Member Annotation</span></span>

<span data-ttu-id="0e534-156">Los atributos de seguridad que se aplican a un tipo también se aplican a los miembros que el tipo introduce.</span><span class="sxs-lookup"><span data-stu-id="0e534-156">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="0e534-157">Sin embargo, no se aplican a invalidaciones virtuales o abstractas de la clase base o implementaciones de interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e534-157">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="0e534-158">Las reglas siguientes se aplican al uso de atributos en el nivel de tipo y miembro:</span><span class="sxs-lookup"><span data-stu-id="0e534-158">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="0e534-159">`SecurityCritical`: el tipo o miembro es crítico y solo lo puede invocar código de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0e534-159">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="0e534-160">Los métodos que se introducen en un tipo crítico para la seguridad son críticos.</span><span class="sxs-lookup"><span data-stu-id="0e534-160">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0e534-161">Los métodos abstractos y virtuales que se introducen en interfaces o clases base y que se invalidan o se implementan en una clase crítica para la seguridad son transparentes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0e534-161">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="0e534-162">Se deben identificar como `SecuritySafeCritical` o `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="0e534-162">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="0e534-163">`SecuritySafeCritical`: el tipo o miembro es crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e534-163">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="0e534-164">Sin embargo, puede llamarse al tipo o miembro desde código transparente (de confianza parcial) y es tan capaz como cualquier otro código crítico.</span><span class="sxs-lookup"><span data-stu-id="0e534-164">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="0e534-165">El código se debe auditar para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e534-165">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="0e534-166">Patrones de invalidación</span><span class="sxs-lookup"><span data-stu-id="0e534-166">Override Patterns</span></span>

<span data-ttu-id="0e534-167">La siguiente tabla muestra las invalidaciones de método permitidas para la transparencia de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="0e534-167">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="0e534-168">Miembro base virtual/de interfaz</span><span class="sxs-lookup"><span data-stu-id="0e534-168">Base virtual/interface member</span></span>|<span data-ttu-id="0e534-169">Invalidación/interfaz</span><span class="sxs-lookup"><span data-stu-id="0e534-169">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="0e534-170">Reglas de herencia</span><span class="sxs-lookup"><span data-stu-id="0e534-170">Inheritance Rules</span></span>

<span data-ttu-id="0e534-171">En esta sección, se asigna el siguiente orden a código `Transparent`, `Critical` y `SafeCritical` en función del acceso y las capacidades:</span><span class="sxs-lookup"><span data-stu-id="0e534-171">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="0e534-172">Reglas para tipos: van de izquierda a derecha y el acceso se vuelve más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="0e534-172">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="0e534-173">Los tipos derivados deben ser al menos tan restrictivos como el tipo base.</span><span class="sxs-lookup"><span data-stu-id="0e534-173">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="0e534-174">Reglas para métodos: los métodos derivados no pueden cambiar la accesibilidad del método base.</span><span class="sxs-lookup"><span data-stu-id="0e534-174">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="0e534-175">Para el comportamiento predeterminado, todos los métodos derivados no anotados son `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="0e534-175">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="0e534-176">Los derivados de tipos críticos provocan una excepción que se produce si el método invalidado no está anotado explícitamente como `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="0e534-176">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="0e534-177">En la tabla siguiente se muestran los patrones de herencia de tipo permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e534-177">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="0e534-178">Clase base</span><span class="sxs-lookup"><span data-stu-id="0e534-178">Base class</span></span>|<span data-ttu-id="0e534-179">La clase derivada puede ser</span><span class="sxs-lookup"><span data-stu-id="0e534-179">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="0e534-180">En la tabla siguiente se muestran los patrones de herencia de tipo no permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e534-180">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="0e534-181">Clase base</span><span class="sxs-lookup"><span data-stu-id="0e534-181">Base class</span></span>|<span data-ttu-id="0e534-182">La clase derivada no puede ser</span><span class="sxs-lookup"><span data-stu-id="0e534-182">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="0e534-183">En la tabla siguiente se muestran los patrones de herencia de método permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e534-183">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="0e534-184">Método base</span><span class="sxs-lookup"><span data-stu-id="0e534-184">Base method</span></span>|<span data-ttu-id="0e534-185">El método derivado puede ser</span><span class="sxs-lookup"><span data-stu-id="0e534-185">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="0e534-186">En la tabla siguiente se muestran los patrones de herencia de método no permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e534-186">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="0e534-187">Método base</span><span class="sxs-lookup"><span data-stu-id="0e534-187">Base method</span></span>|<span data-ttu-id="0e534-188">El método derivado no puede ser</span><span class="sxs-lookup"><span data-stu-id="0e534-188">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="0e534-189">Estas reglas de herencia se aplican a los tipos y miembros de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="0e534-189">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="0e534-190">Los tipos de ensamblados de nivel 1 pueden heredar de tipos y miembros críticos para la seguridad de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="0e534-190">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="0e534-191">Por lo tanto, los tipos y miembros de nivel 2 deben tener peticiones de herencia independientes para los herederos de nivel 1.</span><span class="sxs-lookup"><span data-stu-id="0e534-191">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="0e534-192">Información y reglas adicionales</span><span class="sxs-lookup"><span data-stu-id="0e534-192">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="0e534-193">Compatibilidad con LinkDemand</span><span class="sxs-lookup"><span data-stu-id="0e534-193">LinkDemand Support</span></span>

<span data-ttu-id="0e534-194">El modelo de transparencia de nivel 2 reemplaza <xref:System.Security.Permissions.SecurityAction.LinkDemand> con el atributo <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0e534-194">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="0e534-195">En código heredado (nivel 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> se trata automáticamente como <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="0e534-195">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="0e534-196">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0e534-196">Reflection</span></span>

<span data-ttu-id="0e534-197">El hecho de invocar un método crítico o leer un campo crítico desencadena una petición de plena confianza (como si se estuviera invocando un método o campo privados).</span><span class="sxs-lookup"><span data-stu-id="0e534-197">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="0e534-198">Por lo tanto, el código de plena confianza puede invocar un método crítico, mientras que el código de confianza parcial no puede.</span><span class="sxs-lookup"><span data-stu-id="0e534-198">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="0e534-199">Se han agregado las siguientes propiedades al espacio de nombres <xref:System.Reflection> para determinar si el tipo, método o campo es `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> y <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="0e534-199">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="0e534-200">Use estas propiedades para determinar la transparencia mediante la reflexión en lugar de comprobar la presencia del atributo.</span><span class="sxs-lookup"><span data-stu-id="0e534-200">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="0e534-201">Las reglas de transparencia son complejas y la comprobación del atributo podría no ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="0e534-201">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="0e534-202">Un `SafeCritical` método `true` devuelve <xref:System.Type.IsSecurityCritical%2A> <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>tanto `SafeCritical` y , porque es realmente crítico (tiene las mismas capacidades que el código crítico, pero se puede llamar desde código transparente).</span><span class="sxs-lookup"><span data-stu-id="0e534-202">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="0e534-203">Los métodos dinámicos heredan la transparencia de los módulos a los que se adjuntan; no heredan la transparencia del tipo (si están conectados a un tipo).</span><span class="sxs-lookup"><span data-stu-id="0e534-203">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="0e534-204">Omitir la comprobación en plena confianza</span><span class="sxs-lookup"><span data-stu-id="0e534-204">Skip Verification in Full Trust</span></span>

<span data-ttu-id="0e534-205">Puede omitir la comprobación para ensamblados transparentes de plena confianza estableciendo la propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> en `true` en el atributo <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="0e534-205">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="0e534-206">La propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> es `false` de forma predeterminada, por lo que la propiedad debe establecerse en `true` para omitir la comprobación.</span><span class="sxs-lookup"><span data-stu-id="0e534-206">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="0e534-207">Esto debe hacerse únicamente con fines de optimización.</span><span class="sxs-lookup"><span data-stu-id="0e534-207">This should be done for optimization purposes only.</span></span> <span data-ttu-id="0e534-208">Debe asegurarse de que el código transparente del `transparent` ensamblado es comprobable mediante la opción de la [herramienta PEVerify](../tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="0e534-208">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e534-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e534-209">See also</span></span>

- [<span data-ttu-id="0e534-210">Código transparente de seguridad, nivel 1</span><span class="sxs-lookup"><span data-stu-id="0e534-210">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="0e534-211">Cambios en la seguridad</span><span class="sxs-lookup"><span data-stu-id="0e534-211">Security Changes</span></span>](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
