---
title: Código transparente en seguridad, nivel 2
description: Comprenda el código transparente de nivel 2. Vea ejemplos de uso y comportamientos, invalidar patrones, reglas de herencia, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: 3b87a48ac3f9925fd868be9e58d5904014ca6c09
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309214"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="01a26-104">Código transparente en seguridad, nivel 2</span><span class="sxs-lookup"><span data-stu-id="01a26-104">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="01a26-105">La transparencia de nivel 2 se presentó en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="01a26-105">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="01a26-106">Los tres principios de este modelo son código transparente, código crítico para la seguridad y disponible desde código transparente, y código crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="01a26-106">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="01a26-107">El código transparente, incluido el código que se ejecuta como de plena confianza, solo puede llamar a otro código transparente o a código crítico para la seguridad y disponible desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-107">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="01a26-108">Solo puede realizar acciones permitidas por el conjunto de permisos de confianza parcial del dominio (si existe).</span><span class="sxs-lookup"><span data-stu-id="01a26-108">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="01a26-109">El código transparente no puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01a26-109">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="01a26-110">Realizar una instrucción <xref:System.Security.CodeAccessPermission.Assert%2A> o una elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="01a26-110">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="01a26-111">Contener código no seguro o no comprobable.</span><span class="sxs-lookup"><span data-stu-id="01a26-111">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="01a26-112">Llamar directamente a código crítico.</span><span class="sxs-lookup"><span data-stu-id="01a26-112">Directly call critical code.</span></span>

  - <span data-ttu-id="01a26-113">Llamar a código nativo o código con el atributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01a26-113">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="01a26-114">Llamar a un miembro que está protegido por <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span><span class="sxs-lookup"><span data-stu-id="01a26-114">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="01a26-115">Heredar de tipos críticos.</span><span class="sxs-lookup"><span data-stu-id="01a26-115">Inherit from critical types.</span></span>

  <span data-ttu-id="01a26-116">Además, los métodos transparentes no pueden invalidar métodos virtuales críticos o implementar métodos de interfaz críticos.</span><span class="sxs-lookup"><span data-stu-id="01a26-116">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="01a26-117">El código crítico para la seguridad es de plena confianza, pero el código transparente puede llamarlo.</span><span class="sxs-lookup"><span data-stu-id="01a26-117">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="01a26-118">Expone un área expuesta limitada de código de plena confianza; las comprobaciones de corrección y seguridad se producen en código crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="01a26-118">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="01a26-119">El código crítico para la seguridad puede llamar a cualquier código y es de plena confianza, pero no se puede llamar mediante código transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-119">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="01a26-120">Ejemplos de uso y comportamientos</span><span class="sxs-lookup"><span data-stu-id="01a26-120">Usage Examples and Behaviors</span></span>

<span data-ttu-id="01a26-121">Para especificar .NET Framework 4 reglas (transparencia de nivel 2), use la siguiente anotación para un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="01a26-121">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="01a26-122">Para bloquear en las reglas de .NET Framework 2.0 (transparencia de nivel 1), use la siguiente anotación:</span><span class="sxs-lookup"><span data-stu-id="01a26-122">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="01a26-123">Si no anota un ensamblado, se usan las reglas de .NET Framework 4 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01a26-123">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="01a26-124">Sin embargo, el procedimiento recomendado es usar el <xref:System.Security.SecurityRulesAttribute> atributo en lugar de depender del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="01a26-124">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="01a26-125">Anotación de todo el ensamblado</span><span class="sxs-lookup"><span data-stu-id="01a26-125">Assembly-wide Annotation</span></span>

<span data-ttu-id="01a26-126">Las reglas siguientes se aplican al uso de atributos en el nivel de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="01a26-126">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="01a26-127">Ningún atributo: si no se especifica ningún atributo, el tiempo de ejecución interpreta todo el código como crítico para la seguridad, excepto cuando por el hecho de ser crítico para la seguridad infringe una regla de herencia (por ejemplo, al invalidar o implementar un método de interfaz o virtual transparente).</span><span class="sxs-lookup"><span data-stu-id="01a26-127">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="01a26-128">En esos casos, los métodos son críticos para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="01a26-128">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="01a26-129">Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01a26-129">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="01a26-130">`SecurityTransparent`: todo el código es transparente; el ensamblado completo no hará nada que tenga privilegios o no sea seguro.</span><span class="sxs-lookup"><span data-stu-id="01a26-130">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="01a26-131">`SecurityCritical`: todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-131">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="01a26-132">Este escenario se parece a cuando no se especifica ningún atributo; sin embargo, Common Language Runtime no determina automáticamente las reglas de transparencia.</span><span class="sxs-lookup"><span data-stu-id="01a26-132">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="01a26-133">Por ejemplo, si invalida un método virtual o abstracto o si implementa un método de interfaz, de forma predeterminada, ese método es transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-133">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="01a26-134">Debe anotar explícitamente el método como `SecurityCritical` o `SecuritySafeCritical`; de lo contrario, se producirá una <xref:System.TypeLoadException> en tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="01a26-134">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="01a26-135">Esta regla también se aplica cuando la clase base y la clase derivada están en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="01a26-135">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="01a26-136">`AllowPartiallyTrustedCallers` (solo nivel 2): el valor predeterminado de todo el código es transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-136">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="01a26-137">Sin embargo, los miembros y tipos individuales pueden tener otros atributos.</span><span class="sxs-lookup"><span data-stu-id="01a26-137">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="01a26-138">En la tabla siguiente se compara el comportamiento de nivel de ensamblado para el nivel 2 con el nivel 1.</span><span class="sxs-lookup"><span data-stu-id="01a26-138">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="01a26-139">Atributo de ensamblado</span><span class="sxs-lookup"><span data-stu-id="01a26-139">Assembly attribute</span></span>|<span data-ttu-id="01a26-140">Nivel 2</span><span class="sxs-lookup"><span data-stu-id="01a26-140">Level 2</span></span>|<span data-ttu-id="01a26-141">Nivel 1</span><span class="sxs-lookup"><span data-stu-id="01a26-141">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="01a26-142">Ningún atributo en un ensamblado de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="01a26-142">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="01a26-143">Los tipos y los miembros son transparentes de forma predeterminada, pero pueden ser críticos para la seguridad o bien críticos para la seguridad y disponibles desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-143">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="01a26-144">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="01a26-144">All types and members are transparent.</span></span>|
|<span data-ttu-id="01a26-145">Ningún atributo</span><span class="sxs-lookup"><span data-stu-id="01a26-145">No attribute</span></span>|<span data-ttu-id="01a26-146">Si no se especifica ningún atributo, Common Language Runtime determina las reglas de transparencia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01a26-146">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="01a26-147">Todos los tipos y los miembros son críticos para la seguridad, excepto cuando el hecho de ser críticos para la seguridad infringe una regla de herencia.</span><span class="sxs-lookup"><span data-stu-id="01a26-147">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="01a26-148">En un ensamblado de plena confianza (en la caché global de ensamblados, o identificado como de plena confianza en `AppDomain`), todos los tipos son transparentes y todos los miembros son críticos para la seguridad y disponibles desde código transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-148">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="01a26-149">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="01a26-149">All types and members are transparent.</span></span>|<span data-ttu-id="01a26-150">Todos los tipos y los miembros son transparentes.</span><span class="sxs-lookup"><span data-stu-id="01a26-150">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="01a26-151">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="01a26-151">Not applicable.</span></span>|<span data-ttu-id="01a26-152">Todos los tipos y los miembros son críticos para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="01a26-152">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="01a26-153">Todo el código introducido por tipos en este ensamblado es crítico; el código restante es transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-153">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="01a26-154">Si invalida un método virtual o abstracto o si implementa un método de interfaz, debe anotar explícitamente ese método como `SecurityCritical` o `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="01a26-154">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="01a26-155">El valor predeterminado de todo el código es transparente.</span><span class="sxs-lookup"><span data-stu-id="01a26-155">All code defaults to transparent.</span></span> <span data-ttu-id="01a26-156">Sin embargo, los miembros y tipos individuales pueden tener otros atributos.</span><span class="sxs-lookup"><span data-stu-id="01a26-156">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="01a26-157">Anotación de tipos y de miembros</span><span class="sxs-lookup"><span data-stu-id="01a26-157">Type and Member Annotation</span></span>

<span data-ttu-id="01a26-158">Los atributos de seguridad que se aplican a un tipo también se aplican a los miembros que el tipo introduce.</span><span class="sxs-lookup"><span data-stu-id="01a26-158">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="01a26-159">Sin embargo, no se aplican a invalidaciones virtuales o abstractas de la clase base o implementaciones de interfaz.</span><span class="sxs-lookup"><span data-stu-id="01a26-159">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="01a26-160">Las reglas siguientes se aplican al uso de atributos en el nivel de tipo y miembro:</span><span class="sxs-lookup"><span data-stu-id="01a26-160">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="01a26-161">`SecurityCritical`: el tipo o miembro es crítico y solo lo puede invocar código de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="01a26-161">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="01a26-162">Los métodos que se introducen en un tipo crítico para la seguridad son críticos.</span><span class="sxs-lookup"><span data-stu-id="01a26-162">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="01a26-163">Los métodos abstractos y virtuales que se introducen en interfaces o clases base y que se invalidan o se implementan en una clase crítica para la seguridad son transparentes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01a26-163">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="01a26-164">Se deben identificar como `SecuritySafeCritical` o `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="01a26-164">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="01a26-165">`SecuritySafeCritical`: el tipo o miembro es crítico para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="01a26-165">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="01a26-166">Sin embargo, puede llamarse al tipo o miembro desde código transparente (de confianza parcial) y es tan capaz como cualquier otro código crítico.</span><span class="sxs-lookup"><span data-stu-id="01a26-166">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="01a26-167">El código se debe auditar para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="01a26-167">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="01a26-168">Patrones de invalidación</span><span class="sxs-lookup"><span data-stu-id="01a26-168">Override Patterns</span></span>

<span data-ttu-id="01a26-169">La siguiente tabla muestra las invalidaciones de método permitidas para la transparencia de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="01a26-169">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="01a26-170">Miembro base virtual/de interfaz</span><span class="sxs-lookup"><span data-stu-id="01a26-170">Base virtual/interface member</span></span>|<span data-ttu-id="01a26-171">Invalidación/interfaz</span><span class="sxs-lookup"><span data-stu-id="01a26-171">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="01a26-172">Reglas de herencia</span><span class="sxs-lookup"><span data-stu-id="01a26-172">Inheritance Rules</span></span>

<span data-ttu-id="01a26-173">En esta sección, se asigna el siguiente orden a código `Transparent`, `Critical` y `SafeCritical` en función del acceso y las capacidades:</span><span class="sxs-lookup"><span data-stu-id="01a26-173">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="01a26-174">Reglas para tipos: van de izquierda a derecha y el acceso se vuelve más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="01a26-174">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="01a26-175">Los tipos derivados deben ser al menos tan restrictivos como el tipo base.</span><span class="sxs-lookup"><span data-stu-id="01a26-175">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="01a26-176">Reglas para métodos: los métodos derivados no pueden cambiar la accesibilidad del método base.</span><span class="sxs-lookup"><span data-stu-id="01a26-176">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="01a26-177">Para el comportamiento predeterminado, todos los métodos derivados no anotados son `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="01a26-177">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="01a26-178">Los derivados de tipos críticos provocan una excepción que se produce si el método invalidado no está anotado explícitamente como `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="01a26-178">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="01a26-179">En la tabla siguiente se muestran los patrones de herencia de tipo permitidos.</span><span class="sxs-lookup"><span data-stu-id="01a26-179">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="01a26-180">Clase base</span><span class="sxs-lookup"><span data-stu-id="01a26-180">Base class</span></span>|<span data-ttu-id="01a26-181">La clase derivada puede ser</span><span class="sxs-lookup"><span data-stu-id="01a26-181">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="01a26-182">En la tabla siguiente se muestran los patrones de herencia de tipo no permitidos.</span><span class="sxs-lookup"><span data-stu-id="01a26-182">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="01a26-183">Clase base</span><span class="sxs-lookup"><span data-stu-id="01a26-183">Base class</span></span>|<span data-ttu-id="01a26-184">La clase derivada no puede ser</span><span class="sxs-lookup"><span data-stu-id="01a26-184">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="01a26-185">En la tabla siguiente se muestran los patrones de herencia de método permitidos.</span><span class="sxs-lookup"><span data-stu-id="01a26-185">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="01a26-186">Método base</span><span class="sxs-lookup"><span data-stu-id="01a26-186">Base method</span></span>|<span data-ttu-id="01a26-187">El método derivado puede ser</span><span class="sxs-lookup"><span data-stu-id="01a26-187">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="01a26-188">En la tabla siguiente se muestran los patrones de herencia de método no permitidos.</span><span class="sxs-lookup"><span data-stu-id="01a26-188">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="01a26-189">Método base</span><span class="sxs-lookup"><span data-stu-id="01a26-189">Base method</span></span>|<span data-ttu-id="01a26-190">El método derivado no puede ser</span><span class="sxs-lookup"><span data-stu-id="01a26-190">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="01a26-191">Estas reglas de herencia se aplican a los tipos y miembros de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="01a26-191">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="01a26-192">Los tipos de ensamblados de nivel 1 pueden heredar de tipos y miembros críticos para la seguridad de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="01a26-192">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="01a26-193">Por lo tanto, los tipos y miembros de nivel 2 deben tener peticiones de herencia independientes para los herederos de nivel 1.</span><span class="sxs-lookup"><span data-stu-id="01a26-193">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="01a26-194">Información y reglas adicionales</span><span class="sxs-lookup"><span data-stu-id="01a26-194">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="01a26-195">Compatibilidad con LinkDemand</span><span class="sxs-lookup"><span data-stu-id="01a26-195">LinkDemand Support</span></span>

<span data-ttu-id="01a26-196">El modelo de transparencia de nivel 2 reemplaza <xref:System.Security.Permissions.SecurityAction.LinkDemand> con el atributo <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01a26-196">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="01a26-197">En código heredado (nivel 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> se trata automáticamente como <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="01a26-197">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="01a26-198">Reflexión</span><span class="sxs-lookup"><span data-stu-id="01a26-198">Reflection</span></span>

<span data-ttu-id="01a26-199">El hecho de invocar un método crítico o leer un campo crítico desencadena una petición de plena confianza (como si se estuviera invocando un método o campo privados).</span><span class="sxs-lookup"><span data-stu-id="01a26-199">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="01a26-200">Por lo tanto, el código de plena confianza puede invocar un método crítico, mientras que el código de confianza parcial no puede.</span><span class="sxs-lookup"><span data-stu-id="01a26-200">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="01a26-201">Se han agregado las siguientes propiedades al espacio de nombres <xref:System.Reflection> para determinar si el tipo, método o campo es `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> y <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="01a26-201">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="01a26-202">Use estas propiedades para determinar la transparencia mediante la reflexión en lugar de comprobar la presencia del atributo.</span><span class="sxs-lookup"><span data-stu-id="01a26-202">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="01a26-203">Las reglas de transparencia son complejas y la comprobación del atributo podría no ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="01a26-203">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="01a26-204">Un `SafeCritical` método devuelve `true` para <xref:System.Type.IsSecurityCritical%2A> y <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> , porque `SafeCritical` es realmente crítico (tiene las mismas funcionalidades que el código crítico, pero se puede llamar desde código transparente).</span><span class="sxs-lookup"><span data-stu-id="01a26-204">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="01a26-205">Los métodos dinámicos heredan la transparencia de los módulos a los que se adjuntan; no heredan la transparencia del tipo (si están conectados a un tipo).</span><span class="sxs-lookup"><span data-stu-id="01a26-205">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="01a26-206">Omitir la comprobación en plena confianza</span><span class="sxs-lookup"><span data-stu-id="01a26-206">Skip Verification in Full Trust</span></span>

<span data-ttu-id="01a26-207">Puede omitir la comprobación para ensamblados transparentes de plena confianza estableciendo la propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> en `true` en el atributo <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="01a26-207">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="01a26-208">La propiedad <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> es `false` de forma predeterminada, por lo que la propiedad debe establecerse en `true` para omitir la comprobación.</span><span class="sxs-lookup"><span data-stu-id="01a26-208">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="01a26-209">Esto debe hacerse únicamente con fines de optimización.</span><span class="sxs-lookup"><span data-stu-id="01a26-209">This should be done for optimization purposes only.</span></span> <span data-ttu-id="01a26-210">Debe asegurarse de que el código transparente del ensamblado se puede comprobar mediante la `transparent` opción de la [herramienta peverify](../tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="01a26-210">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="01a26-211">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01a26-211">See also</span></span>

- [<span data-ttu-id="01a26-212">Código transparente en seguridad, nivel 1</span><span class="sxs-lookup"><span data-stu-id="01a26-212">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="01a26-213">Cambios de seguridad</span><span class="sxs-lookup"><span data-stu-id="01a26-213">Security Changes</span></span>](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
