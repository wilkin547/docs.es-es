---
title: Compatibilidad con la directiva de seguridad de acceso del código y migración
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: 949739b3336a9182eef583cc405e60e09d7ec09d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217159"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="24d60-102">Compatibilidad con la directiva de seguridad de acceso del código y migración</span><span class="sxs-lookup"><span data-stu-id="24d60-102">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="24d60-103">La parte de la Directiva de seguridad de acceso del código (CAS) se ha convertido en obsoleta en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="24d60-103">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="24d60-104">Como resultado, puede encontrar advertencias de compilación y excepciones en tiempo de ejecución si llama a los tipos y miembros obsoletos de la directiva [explícita](#explicit_use) o [implícitamente](#implicit_use) (a través de otros tipos y miembros).</span><span class="sxs-lookup"><span data-stu-id="24d60-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="24d60-105">Para los errores y advertencias:</span><span class="sxs-lookup"><span data-stu-id="24d60-105">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="24d60-106">[Migrar](#migration) a los reemplazos .NET Framework 4 para las llamadas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="24d60-106">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="24d60-107">\- O bien</span><span class="sxs-lookup"><span data-stu-id="24d60-107">\- or -</span></span>

- <span data-ttu-id="24d60-108">Mediante el [\<NetFx40_LegacySecurityPolicy > elemento de configuración](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) para participar en el comportamiento de la Directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="24d60-108">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="24d60-109">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="24d60-109">This topic contains the following sections:</span></span>

- [<span data-ttu-id="24d60-110">Uso explícito</span><span class="sxs-lookup"><span data-stu-id="24d60-110">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="24d60-111">Uso implícito</span><span class="sxs-lookup"><span data-stu-id="24d60-111">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="24d60-112">Errores y advertencias</span><span class="sxs-lookup"><span data-stu-id="24d60-112">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="24d60-113">Migración: reemplazo de llamadas obsoletas</span><span class="sxs-lookup"><span data-stu-id="24d60-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="24d60-114">Compatibilidad: uso de la opción heredado de directiva CAS</span><span class="sxs-lookup"><span data-stu-id="24d60-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="24d60-115">Uso explícito</span><span class="sxs-lookup"><span data-stu-id="24d60-115">Explicit Use</span></span>

<span data-ttu-id="24d60-116">Los miembros que manipulan directamente directivas de seguridad o que necesitan la directiva CAS para el espacio aislado están obsoletos y generarán errores de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="24d60-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="24d60-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24d60-117">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="24d60-118">Uso implícito</span><span class="sxs-lookup"><span data-stu-id="24d60-118">Implicit Use</span></span>

<span data-ttu-id="24d60-119">Cuando varios ensamblados cargan sobrecargas se producen errores debido a su uso implícito de la directiva CAS.</span><span class="sxs-lookup"><span data-stu-id="24d60-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="24d60-120">Estas sobrecargas toman un parámetro <xref:System.Security.Policy.Evidence> que se usa para resolver la directiva CAS y proporcionar un conjunto de permisos concedidos a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="24d60-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="24d60-121">Estos son algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="24d60-121">Here are some examples.</span></span> <span data-ttu-id="24d60-122">Las sobrecargas obsoletas son las que toman <xref:System.Security.Policy.Evidence> como parámetro:</span><span class="sxs-lookup"><span data-stu-id="24d60-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="24d60-123">Errores y advertencias</span><span class="sxs-lookup"><span data-stu-id="24d60-123">Errors and Warnings</span></span>

<span data-ttu-id="24d60-124">Los tipos y miembros obsoletos generan los siguientes mensajes de error cuando se usan.</span><span class="sxs-lookup"><span data-stu-id="24d60-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="24d60-125">Tenga en cuenta que el tipo <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> en sí no está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="24d60-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="24d60-126">Advertencia en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="24d60-126">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="24d60-127">Excepción de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="24d60-127">Run-time exception:</span></span>

<span data-ttu-id="24d60-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="24d60-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="24d60-129">Migración: reemplazo para las llamadas obsoletas</span><span class="sxs-lookup"><span data-stu-id="24d60-129">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="24d60-130">Determinar el nivel de confianza de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="24d60-130">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="24d60-131">La directiva CAS suele usarse para determinar el nivel de confianza o el conjunto de permisos concedidos a un ensamblado o dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="24d60-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="24d60-132">El .NET Framework 4 expone las siguientes propiedades útiles que no necesitan resolver la Directiva de seguridad:</span><span class="sxs-lookup"><span data-stu-id="24d60-132">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="24d60-133">Espacio aislado del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="24d60-133">Application Domain Sandboxing</span></span>

<span data-ttu-id="24d60-134">El método <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> suele usarse para hospedar en un espacio aislado los ensamblados de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="24d60-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="24d60-135">El .NET Framework 4 expone los miembros que no tienen que usar <xref:System.Security.Policy.PolicyLevel> para este fin.</span><span class="sxs-lookup"><span data-stu-id="24d60-135">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="24d60-136">Para obtener más información, consulte [Cómo: ejecutar código de confianza parcial en un espacio aislado](how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="24d60-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="24d60-137">Determinar el conjunto de permisos seguro o razonable para código de confianza parcial</span><span class="sxs-lookup"><span data-stu-id="24d60-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="24d60-138">Los hosts suelen necesitar determinar los permisos adecuados para el código hospedado en espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="24d60-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="24d60-139">Antes de la .NET Framework 4, la Directiva de CAS proporcionaba una forma de hacerlo con el método <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="24d60-139">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="24d60-140">Como reemplazo, .NET Framework 4 proporciona el método <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType>, que devuelve un conjunto de permisos estándar seguro para la evidencia proporcionada.</span><span class="sxs-lookup"><span data-stu-id="24d60-140">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="24d60-141">Escenarios sin espacio aislado: sobrecargas para cargas de ensamblado</span><span class="sxs-lookup"><span data-stu-id="24d60-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="24d60-142">La razón para usar una sobrecarga de carga de ensamblado puede ser usar parámetros que de otra forma no están disponibles, en lugar de hospedar el ensamblado en un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="24d60-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="24d60-143">A partir de la .NET Framework 4, las sobrecargas de carga de ensamblados que no requieren un objeto <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> como parámetro, por ejemplo, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, habilitan este escenario.</span><span class="sxs-lookup"><span data-stu-id="24d60-143">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="24d60-144">Si quiere hospedar un ensamblado en un espacio aislado, use la sobrecarga <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="24d60-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="24d60-145">Compatibilidad: usar la opción de directiva CAS heredada</span><span class="sxs-lookup"><span data-stu-id="24d60-145">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="24d60-146">El [\<NetFx40_LegacySecurityPolicy > elemento de configuración](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) permite especificar que un proceso o una biblioteca utiliza una directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="24d60-146">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="24d60-147">Cuando se habilita este elemento, las sobrecargas de directiva y de evidencia funcionarán igual que en versiones anteriores de Framework.</span><span class="sxs-lookup"><span data-stu-id="24d60-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="24d60-148">El comportamiento de la directiva CAS es específico de cada versión del tiempo de ejecución y por lo tanto, modificar la directiva CAS para una versión del tiempo de ejecución no afecta a la directiva CAS de otra versión.</span><span class="sxs-lookup"><span data-stu-id="24d60-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="24d60-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24d60-149">See also</span></span>

- [<span data-ttu-id="24d60-150">Cómo: Ejecutar código de confianza parcial en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="24d60-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="24d60-151">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="24d60-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
