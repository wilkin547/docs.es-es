---
title: <useLegacyJit> (Elemento)
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968851"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="daa09-102">\<useLegacyJit> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="daa09-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="daa09-103">Determina si Common Language Runtime usa el compilador JIT de 64 bits heredado para la compilación Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="daa09-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**  
  
## <a name="syntax"></a><span data-ttu-id="daa09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="daa09-104">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="daa09-105">El nombre del elemento `useLegacyJit` distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="daa09-105">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="daa09-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="daa09-106">Attributes and elements</span></span>

<span data-ttu-id="daa09-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="daa09-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="daa09-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="daa09-108">Attributes</span></span>  
  
| <span data-ttu-id="daa09-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="daa09-109">Attribute</span></span> | <span data-ttu-id="daa09-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="daa09-110">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="daa09-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="daa09-111">Required attribute.</span></span><br><br><span data-ttu-id="daa09-112">Especifica si el motor en tiempo de ejecución utiliza el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="daa09-112">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="daa09-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="daa09-113">enabled attribute</span></span>  
  
| <span data-ttu-id="daa09-114">Value</span><span class="sxs-lookup"><span data-stu-id="daa09-114">Value</span></span> | <span data-ttu-id="daa09-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="daa09-115">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="daa09-116">0</span><span class="sxs-lookup"><span data-stu-id="daa09-116">0</span></span>     | <span data-ttu-id="daa09-117">En el Common Language Runtime se usa el nuevo compilador JIT de 64 bits incluido en el .NET Framework 4,6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="daa09-117">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="daa09-118">1</span><span class="sxs-lookup"><span data-stu-id="daa09-118">1</span></span>     | <span data-ttu-id="daa09-119">En el Common Language Runtime se usa el compilador JIT de 64 bits anterior.</span><span class="sxs-lookup"><span data-stu-id="daa09-119">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="daa09-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="daa09-120">Child elements</span></span>

<span data-ttu-id="daa09-121">None</span><span class="sxs-lookup"><span data-stu-id="daa09-121">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="daa09-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="daa09-122">Parent elements</span></span>  
  
| <span data-ttu-id="daa09-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="daa09-123">Element</span></span>         | <span data-ttu-id="daa09-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="daa09-124">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="daa09-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="daa09-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="daa09-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="daa09-126">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="daa09-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="daa09-127">Remarks</span></span>  

<span data-ttu-id="daa09-128">A partir de la .NET Framework 4,6, el Common Language Runtime utiliza de forma predeterminada un nuevo compilador de 64 bits para la compilación Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="daa09-128">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="daa09-129">En algunos casos, esto puede dar lugar a una diferencia en el comportamiento del código de la aplicación que compiló JIT por la versión anterior del compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="daa09-129">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="daa09-130">Al establecer el `enabled` atributo del `<useLegacyJit>` elemento en `1` , puede deshabilitar el nuevo compilador JIT de 64 bits y compilar la aplicación con el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="daa09-130">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="daa09-131">El `<useLegacyJit>` elemento afecta solo a la compilación JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="daa09-131">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="daa09-132">La compilación con el compilador JIT de 32 bits no se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="daa09-132">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="daa09-133">En lugar de utilizar un valor de archivo de configuración, puede habilitar el compilador JIT de 64 bits heredado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="daa09-133">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="daa09-134">Establecer una variable de entorno</span><span class="sxs-lookup"><span data-stu-id="daa09-134">Setting an environment variable</span></span>

  <span data-ttu-id="daa09-135">Establezca la `COMPLUS_useLegacyJit` variable de entorno en `0` (use el nuevo compilador jit de 64 bits) o `1` (use el anterior compilador JIT de 64 bits):</span><span class="sxs-lookup"><span data-stu-id="daa09-135">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="daa09-136">La variable de entorno tiene *ámbito global*, lo que significa que afecta a todas las aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="daa09-136">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="daa09-137">Si se establece, puede reemplazarse por la configuración del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="daa09-137">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="daa09-138">El nombre de la variable de entorno no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="daa09-138">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="daa09-139">Agregar una clave del registro</span><span class="sxs-lookup"><span data-stu-id="daa09-139">Adding a registry key</span></span>

  <span data-ttu-id="daa09-140">Puede habilitar el compilador JIT de 64 bits heredado agregando un `REG_DWORD` valor a `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave o del registro.</span><span class="sxs-lookup"><span data-stu-id="daa09-140">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="daa09-141">El valor se denomina `useLegacyJit` .</span><span class="sxs-lookup"><span data-stu-id="daa09-141">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="daa09-142">Si el valor es 0, se utiliza el nuevo compilador.</span><span class="sxs-lookup"><span data-stu-id="daa09-142">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="daa09-143">Si el valor es 1, el compilador JIT de 64 bits heredado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="daa09-143">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="daa09-144">El nombre del valor de registro no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="daa09-144">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="daa09-145">Agregar el valor a la `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones que se ejecutan en la máquina.</span><span class="sxs-lookup"><span data-stu-id="daa09-145">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="daa09-146">Agregar el valor a la `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` clave afecta a todas las aplicaciones ejecutadas por el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="daa09-146">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="daa09-147">Si un equipo se configura con varias cuentas de usuario, solo se verán afectadas las aplicaciones ejecutadas por el usuario actual, a menos que el valor se agregue también a las claves del registro para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="daa09-147">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="daa09-148">Al agregar el `<useLegacyJit>` elemento a un archivo de configuración, se invalida la configuración del registro, si está presente.</span><span class="sxs-lookup"><span data-stu-id="daa09-148">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daa09-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="daa09-149">Example</span></span>  

<span data-ttu-id="daa09-150">El siguiente archivo de configuración deshabilita la compilación con el nuevo compilador JIT de 64 bits y, en su lugar, utiliza el compilador JIT de 64 bits heredado.</span><span class="sxs-lookup"><span data-stu-id="daa09-150">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="daa09-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="daa09-151">See also</span></span>

- [<span data-ttu-id="daa09-152">\<runtime>Element</span><span class="sxs-lookup"><span data-stu-id="daa09-152">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="daa09-153">\<configuration>Element</span><span class="sxs-lookup"><span data-stu-id="daa09-153">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="daa09-154">Mitigación: Nuevo compilador JIT de 64 bits</span><span class="sxs-lookup"><span data-stu-id="daa09-154">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
