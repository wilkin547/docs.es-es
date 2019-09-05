---
title: <useLegacyJit> (Elemento)
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b783a82b1ef964de308532ef544bbfab2397400
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252223"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="394de-102">Elemento \<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="394de-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="394de-103">Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="394de-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="394de-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="394de-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="394de-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="394de-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="394de-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<useLegacyJit>**</span><span class="sxs-lookup"><span data-stu-id="394de-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="394de-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="394de-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="394de-108">El nombre `useLegacyJit` del elemento distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="394de-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="394de-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="394de-109">Attributes and elements</span></span>

<span data-ttu-id="394de-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="394de-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="394de-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="394de-111">Attributes</span></span>  
  
| <span data-ttu-id="394de-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="394de-112">Attribute</span></span> | <span data-ttu-id="394de-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="394de-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="394de-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="394de-114">Required attribute.</span></span><br><br><span data-ttu-id="394de-115">Especifica si el motor en tiempo de ejecución utiliza el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="394de-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="394de-116">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="394de-116">enabled attribute</span></span>  
  
| <span data-ttu-id="394de-117">Value</span><span class="sxs-lookup"><span data-stu-id="394de-117">Value</span></span> | <span data-ttu-id="394de-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="394de-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="394de-119">0</span><span class="sxs-lookup"><span data-stu-id="394de-119">0</span></span>     | <span data-ttu-id="394de-120">En el Common Language Runtime se usa el nuevo compilador JIT de 64 bits incluido en el .NET Framework 4,6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="394de-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="394de-121">1</span><span class="sxs-lookup"><span data-stu-id="394de-121">1</span></span>     | <span data-ttu-id="394de-122">En el Common Language Runtime se usa el compilador JIT de 64 bits anterior.</span><span class="sxs-lookup"><span data-stu-id="394de-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="394de-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="394de-123">Child elements</span></span>

<span data-ttu-id="394de-124">None</span><span class="sxs-lookup"><span data-stu-id="394de-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="394de-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="394de-125">Parent elements</span></span>  
  
| <span data-ttu-id="394de-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="394de-126">Element</span></span>         | <span data-ttu-id="394de-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="394de-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="394de-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="394de-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="394de-129">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="394de-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="394de-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="394de-130">Remarks</span></span>  

<span data-ttu-id="394de-131">A partir de la .NET Framework 4,6, el Common Language Runtime utiliza de forma predeterminada un nuevo compilador de 64 bits para la compilación Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="394de-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="394de-132">En algunos casos, esto puede dar lugar a una diferencia en el comportamiento del código de la aplicación que compiló JIT por la versión anterior del compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="394de-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="394de-133">Al establecer el `enabled` atributo `<useLegacyJit>` del elemento en `1`, puede deshabilitar el nuevo compilador JIT de 64 bits y compilar la aplicación con el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="394de-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="394de-134">El `<useLegacyJit>` elemento afecta solo a la compilación JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="394de-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="394de-135">La compilación con el compilador JIT de 32 bits no se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="394de-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="394de-136">En lugar de utilizar un valor de archivo de configuración, puede habilitar el compilador JIT de 64 bits heredado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="394de-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="394de-137">Establecer una variable de entorno</span><span class="sxs-lookup"><span data-stu-id="394de-137">Setting an environment variable</span></span>

  <span data-ttu-id="394de-138">Establezca la `COMPLUS_useLegacyJit` variable de entorno `0` en (use el nuevo compilador JIT de 64 bits `1` ) o (use el anterior compilador JIT de 64 bits):</span><span class="sxs-lookup"><span data-stu-id="394de-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="394de-139">La variable de entorno tiene *ámbito global*, lo que significa que afecta a todas las aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="394de-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="394de-140">Si se establece, puede reemplazarse por la configuración del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="394de-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="394de-141">El nombre de la variable de entorno no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="394de-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="394de-142">Agregar una clave del registro</span><span class="sxs-lookup"><span data-stu-id="394de-142">Adding a registry key</span></span>

  <span data-ttu-id="394de-143">Puede habilitar el compilador JIT de 64 bits heredado agregando un `REG_DWORD` valor a la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave o del registro.</span><span class="sxs-lookup"><span data-stu-id="394de-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="394de-144">El valor se denomina `useLegacyJit`.</span><span class="sxs-lookup"><span data-stu-id="394de-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="394de-145">Si el valor es 0, se utiliza el nuevo compilador.</span><span class="sxs-lookup"><span data-stu-id="394de-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="394de-146">Si el valor es 1, el compilador JIT de 64 bits heredado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="394de-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="394de-147">El nombre del valor del registro no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="394de-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="394de-148">Agregar el valor a la `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="394de-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="394de-149">Agregar el valor a la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones ejecutadas por el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="394de-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="394de-150">Si un equipo se configura con varias cuentas de usuario, solo se verán afectadas las aplicaciones ejecutadas por el usuario actual, a menos que el valor se agregue también a las claves del registro para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="394de-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="394de-151">Al agregar `<useLegacyJit>` el elemento a un archivo de configuración, se invalida la configuración del registro, si está presente.</span><span class="sxs-lookup"><span data-stu-id="394de-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="394de-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="394de-152">Example</span></span>  

<span data-ttu-id="394de-153">El siguiente archivo de configuración deshabilita la compilación con el nuevo compilador JIT de 64 bits y, en su lugar, utiliza el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="394de-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="394de-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="394de-154">See also</span></span>

- [<span data-ttu-id="394de-155">\<Elemento > en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="394de-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="394de-156">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="394de-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="394de-157">Mitigación Nuevo compilador JIT de 64 bits</span><span class="sxs-lookup"><span data-stu-id="394de-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
