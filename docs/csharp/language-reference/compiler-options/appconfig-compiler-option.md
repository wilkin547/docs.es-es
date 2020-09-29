---
description: -appconfig (Opciones del compilador de C#)
title: -appconfig (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 8ee481851dc02bed5eb0a7c26fa8893e52d54a9f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157972"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="07179-103">-appconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="07179-103">-appconfig (C# Compiler Options)</span></span>

<span data-ttu-id="07179-104">La opción del compilador **-appconfig** permite a una aplicación de C# especificar la ubicación del archivo de configuración de la aplicación de un ensamblado (app.config) al Common Language Runtime (CLR) en tiempo de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07179-104">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07179-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07179-105">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="07179-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="07179-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="07179-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="07179-107">Required.</span></span> <span data-ttu-id="07179-108">El archivo de configuración de la aplicación que contiene los valores de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07179-108">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07179-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07179-109">Remarks</span></span>  

 <span data-ttu-id="07179-110">Un uso de **-appconfig** es el de escenarios avanzados en los que un ensamblado tiene que hacer referencia a la versión de .NET Framework y a la versión de .NET Framework para Silverlight de un ensamblado de referencia determinado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="07179-110">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="07179-111">Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia al escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye con Silverlight.</span><span class="sxs-lookup"><span data-stu-id="07179-111">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="07179-112">El mismo ensamblado del diseñador tiene que tener acceso a ambos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07179-112">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="07179-113">De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="07179-113">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="07179-114">La opción del compilador **-appconfig** permite especificar la ubicación de un archivo app.config que deshabilita el comportamiento predeterminado usando una etiqueta `<supportPortability>`, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="07179-114">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="07179-115">El compilador pasa la ubicación del archivo a la lógica de enlace del ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="07179-115">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07179-116">Si está usando Microsoft Build Engine (MSBuild) para compilar su aplicación, puede establecer la opción del compilador **-appconfig** mediante la adición de una etiqueta de propiedad al archivo .csproj.</span><span class="sxs-lookup"><span data-stu-id="07179-116">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="07179-117">Para usar el archivo app.config que ya está establecido en el proyecto, agregue la etiqueta `<UseAppConfigForCompiler>` de propiedades al archivo .csproj y establezca su valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="07179-117">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="07179-118">Para especificar otro archivo app.config, agregue la etiqueta `<AppConfigForCompiler>` de propiedades y establezca su valor en la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="07179-118">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07179-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07179-119">Example</span></span>  

 <span data-ttu-id="07179-120">En el siguiente ejemplo se muestra un archivo app.config que permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="07179-120">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="07179-121">La opción del compilador **-appconfig** especifica la ubicación de este archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="07179-121">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07179-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="07179-122">See also</span></span>

- [<span data-ttu-id="07179-123">Elemento \<supportPortability></span><span class="sxs-lookup"><span data-stu-id="07179-123">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [<span data-ttu-id="07179-124">Opciones del compilador de C#, por orden alfabético</span><span class="sxs-lookup"><span data-stu-id="07179-124">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
