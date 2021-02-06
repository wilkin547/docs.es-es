---
description: 'Más información acerca de: <useLegacyJit> elemento'
title: <useLegacyJit> (Elemento)
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a1449cbc69f0aa1b91cc427fbfc5b984bf605169
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640009"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="a075e-103">\<useLegacyJit> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a075e-103">\<useLegacyJit> Element</span></span>

<span data-ttu-id="a075e-104">Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="a075e-104">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**  
  
## <a name="syntax"></a><span data-ttu-id="a075e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a075e-105">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="a075e-106">El nombre del elemento `useLegacyJit` distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a075e-106">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a075e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a075e-107">Attributes and elements</span></span>

<span data-ttu-id="a075e-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a075e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a075e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a075e-109">Attributes</span></span>  
  
| <span data-ttu-id="a075e-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="a075e-110">Attribute</span></span> | <span data-ttu-id="a075e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a075e-111">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="a075e-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a075e-112">Required attribute.</span></span><br><br><span data-ttu-id="a075e-113">Especifica si el motor en tiempo de ejecución utiliza el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="a075e-113">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="a075e-114">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="a075e-114">enabled attribute</span></span>  
  
| <span data-ttu-id="a075e-115">Value</span><span class="sxs-lookup"><span data-stu-id="a075e-115">Value</span></span> | <span data-ttu-id="a075e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a075e-116">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="a075e-117">0</span><span class="sxs-lookup"><span data-stu-id="a075e-117">0</span></span>     | <span data-ttu-id="a075e-118">En el Common Language Runtime se usa el nuevo compilador JIT de 64 bits incluido en el .NET Framework 4,6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a075e-118">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="a075e-119">1</span><span class="sxs-lookup"><span data-stu-id="a075e-119">1</span></span>     | <span data-ttu-id="a075e-120">En el Common Language Runtime se usa el compilador JIT de 64 bits anterior.</span><span class="sxs-lookup"><span data-stu-id="a075e-120">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="a075e-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a075e-121">Child elements</span></span>

<span data-ttu-id="a075e-122">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a075e-122">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="a075e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a075e-123">Parent elements</span></span>  
  
| <span data-ttu-id="a075e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a075e-124">Element</span></span>         | <span data-ttu-id="a075e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a075e-125">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="a075e-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a075e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="a075e-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a075e-127">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="a075e-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a075e-128">Remarks</span></span>  

<span data-ttu-id="a075e-129">A partir de la .NET Framework 4,6, el Common Language Runtime utiliza de forma predeterminada un nuevo compilador de 64 bits para la compilación Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a075e-129">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="a075e-130">En algunos casos, esto puede dar lugar a una diferencia en el comportamiento del código de la aplicación que compiló JIT por la versión anterior del compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a075e-130">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="a075e-131">Al establecer el `enabled` atributo del `<useLegacyJit>` elemento en `1` , puede deshabilitar el nuevo compilador JIT de 64 bits y compilar la aplicación con el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="a075e-131">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a075e-132">El `<useLegacyJit>` elemento afecta solo a la compilación JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a075e-132">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="a075e-133">La compilación con el compilador JIT de 32 bits no se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="a075e-133">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="a075e-134">En lugar de utilizar un valor de archivo de configuración, puede habilitar el compilador JIT de 64 bits heredado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="a075e-134">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="a075e-135">Establecer una variable de entorno</span><span class="sxs-lookup"><span data-stu-id="a075e-135">Setting an environment variable</span></span>

  <span data-ttu-id="a075e-136">Establezca la `COMPLUS_useLegacyJit` variable de entorno en `0` (use el nuevo compilador jit de 64 bits) o `1` (use el anterior compilador JIT de 64 bits):</span><span class="sxs-lookup"><span data-stu-id="a075e-136">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="a075e-137">La variable de entorno tiene *ámbito global*, lo que significa que afecta a todas las aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="a075e-137">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="a075e-138">Si se establece, puede reemplazarse por la configuración del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a075e-138">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="a075e-139">El nombre de la variable de entorno no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a075e-139">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="a075e-140">Agregar una clave del registro</span><span class="sxs-lookup"><span data-stu-id="a075e-140">Adding a registry key</span></span>

  <span data-ttu-id="a075e-141">Puede habilitar el compilador JIT de 64 bits heredado agregando un `REG_DWORD` valor a `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave o del registro.</span><span class="sxs-lookup"><span data-stu-id="a075e-141">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="a075e-142">El valor se denomina `useLegacyJit` .</span><span class="sxs-lookup"><span data-stu-id="a075e-142">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="a075e-143">Si el valor es 0, se utiliza el nuevo compilador.</span><span class="sxs-lookup"><span data-stu-id="a075e-143">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="a075e-144">Si el valor es 1, el compilador JIT de 64 bits heredado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a075e-144">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="a075e-145">El nombre del valor de registro no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a075e-145">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="a075e-146">Agregar el valor a la `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="a075e-146">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="a075e-147">Agregar el valor a la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones ejecutadas por el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a075e-147">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="a075e-148">Si un equipo se configura con varias cuentas de usuario, solo se verán afectadas las aplicaciones ejecutadas por el usuario actual, a menos que el valor se agregue también a las claves del registro para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="a075e-148">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="a075e-149">Al agregar el `<useLegacyJit>` elemento a un archivo de configuración, se invalida la configuración del registro, si está presente.</span><span class="sxs-lookup"><span data-stu-id="a075e-149">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a075e-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a075e-150">Example</span></span>  

<span data-ttu-id="a075e-151">El siguiente archivo de configuración deshabilita la compilación con el nuevo compilador JIT de 64 bits y, en su lugar, utiliza el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="a075e-151">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a075e-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a075e-152">See also</span></span>

- [<span data-ttu-id="a075e-153">Elemento \<runtime></span><span class="sxs-lookup"><span data-stu-id="a075e-153">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="a075e-154">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="a075e-154">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="a075e-155">Mitigación: Nuevo compilador JIT de 64 bits</span><span class="sxs-lookup"><span data-stu-id="a075e-155">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
