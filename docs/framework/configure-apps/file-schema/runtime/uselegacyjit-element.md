---
title: '&lt;useLegacyJit&gt; elemento'
ms.custom: 
ms.date: 04/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d2a71e44db2d6e85ae730f4603bf191f54525c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltuselegacyjitgt-element"></a><span data-ttu-id="7a538-102">&lt;useLegacyJit&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="7a538-102">&lt;useLegacyJit&gt; Element</span></span>

<span data-ttu-id="7a538-103">Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="7a538-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="7a538-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7a538-104">\<configuration></span></span>  
<span data-ttu-id="7a538-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="7a538-105">\<runtime></span></span>  
<span data-ttu-id="7a538-106">\<useLegacyJit ></span><span class="sxs-lookup"><span data-stu-id="7a538-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="7a538-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a538-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="7a538-108">El nombre del elemento `useLegacyJit` distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7a538-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a538-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7a538-109">Attributes and elements</span></span>

<span data-ttu-id="7a538-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7a538-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a538-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a538-111">Attributes</span></span>  
  
| <span data-ttu-id="7a538-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7a538-112">Attribute</span></span> | <span data-ttu-id="7a538-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a538-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="7a538-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7a538-114">Required attribute.</span></span><br><br><span data-ttu-id="7a538-115">Especifica si el runtime usa el antiguo compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7a538-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="7a538-116">atributo enabled</span><span class="sxs-lookup"><span data-stu-id="7a538-116">enabled attribute</span></span>  
  
| <span data-ttu-id="7a538-117">Valor</span><span class="sxs-lookup"><span data-stu-id="7a538-117">Value</span></span> | <span data-ttu-id="7a538-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a538-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="7a538-119">0</span><span class="sxs-lookup"><span data-stu-id="7a538-119">0</span></span>     | <span data-ttu-id="7a538-120">Common language runtime usa el nuevo compilador JIT de 64 bits incluido en el .NET Framework 4.6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7a538-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="7a538-121">1</span><span class="sxs-lookup"><span data-stu-id="7a538-121">1</span></span>     | <span data-ttu-id="7a538-122">Common language runtime usa el antiguo compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7a538-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="7a538-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a538-123">Child elements</span></span>

<span data-ttu-id="7a538-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7a538-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="7a538-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a538-125">Parent elements</span></span>  
  
| <span data-ttu-id="7a538-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a538-126">Element</span></span>         | <span data-ttu-id="7a538-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a538-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="7a538-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a538-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="7a538-129">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a538-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="7a538-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7a538-130">Remarks</span></span>  

<span data-ttu-id="7a538-131">A partir de la versión 4.6 de .NET Framework, common language runtime usa un nuevo compilador de 64 bits para la compilación Just (JIT) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7a538-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="7a538-132">En algunos casos, esto puede dar lugar a una diferencia de comportamiento del código de aplicación que se compila con JIT por la versión anterior del compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7a538-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="7a538-133">Estableciendo la `enabled` atributo de la `<useLegacyJit>` elemento `1`, puede deshabilitar el nuevo compilador JIT de 64 bits y en su lugar, compile la aplicación con el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="7a538-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a538-134">El `<useLegacyJit>` elemento afecta a la compilación de JIT de 64 bits sólo.</span><span class="sxs-lookup"><span data-stu-id="7a538-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="7a538-135">Compilación con el compilador JIT de 32 bits no se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="7a538-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="7a538-136">En lugar de usar un archivo de configuración, puede habilitar el compilador JIT de 64 bits heredado de dos formas:</span><span class="sxs-lookup"><span data-stu-id="7a538-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="7a538-137">Establecer una variable de entorno</span><span class="sxs-lookup"><span data-stu-id="7a538-137">Setting an environment variable</span></span>

  <span data-ttu-id="7a538-138">Establecer el `COMPLUS_useLegacyJit` una variable de entorno `0` (usar el nuevo compilador JIT de 64 bits) o `1` (usar el antiguo compilador JIT de 64 bits):</span><span class="sxs-lookup"><span data-stu-id="7a538-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="7a538-139">La variable de entorno tiene *ámbito global*, lo que significa que afecta a todas las aplicaciones que se ejecutan en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7a538-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="7a538-140">Si establece esta opción, puede reemplazarse por el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a538-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="7a538-141">El nombre de variable de entorno no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7a538-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="7a538-142">Agregar una clave del registro</span><span class="sxs-lookup"><span data-stu-id="7a538-142">Adding a registry key</span></span>

  <span data-ttu-id="7a538-143">Puede habilitar el compilador JIT de 64 bits heredado mediante la adición de un `REG_DWORD` valor como el `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` o `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave en el registro.</span><span class="sxs-lookup"><span data-stu-id="7a538-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="7a538-144">El valor se denomina `useLegacyJit`.</span><span class="sxs-lookup"><span data-stu-id="7a538-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="7a538-145">Si el valor es 0, se utiliza el nuevo compilador.</span><span class="sxs-lookup"><span data-stu-id="7a538-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="7a538-146">Si el valor es 1, se habilita el antiguo compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7a538-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="7a538-147">El nombre del valor del registro no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7a538-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="7a538-148">Agregar el valor para el `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que se ejecutan en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7a538-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="7a538-149">Agregar el valor para el `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que ejecuta el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="7a538-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="7a538-150">Si un equipo está configurado con varias cuentas de usuario, solo las aplicaciones que se ejecuta el usuario actual se ven afectadas, a menos que el valor se agrega a las claves del registro para otros usuarios también.</span><span class="sxs-lookup"><span data-stu-id="7a538-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="7a538-151">Agregar el `<useLegacyJit>` elemento a un archivo de configuración invalida la configuración del registro, si están presentes.</span><span class="sxs-lookup"><span data-stu-id="7a538-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a538-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a538-152">Example</span></span>  

<span data-ttu-id="7a538-153">El archivo de configuración siguiente deshabilita la compilación con el nuevo compilador JIT de 64 bits y en su lugar, usa el antiguo compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7a538-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a538-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a538-154">See also</span></span>

<span data-ttu-id="7a538-155">[\<en tiempo de ejecución > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a538-155">[\<runtime> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) </span></span>  
<span data-ttu-id="7a538-156">[\<Configuración > elemento](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a538-156">[\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
[<span data-ttu-id="7a538-157">Mitigación: Nuevo compilador JIT de 64 bits</span><span class="sxs-lookup"><span data-stu-id="7a538-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
