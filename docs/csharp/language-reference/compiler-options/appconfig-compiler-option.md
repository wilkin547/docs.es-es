---
title: -appconfig (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /appconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2aede966f92af3c94f4591b68732dbdbf5a4c5c9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="appconfig-c-compiler-options"></a><span data-ttu-id="defeb-102">/appconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="defeb-102">/appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="defeb-103">La opción del compilador **/appconfig** permite a una aplicación de C# especificar la ubicación del archivo de configuración de la aplicación de un ensamblado (app.config) al Common Language Runtime (CLR) en tiempo de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="defeb-103">The **/appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="defeb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="defeb-104">Syntax</span></span>  
  
```console  
/appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="defeb-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="defeb-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="defeb-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="defeb-106">Required.</span></span> <span data-ttu-id="defeb-107">El archivo de configuración de la aplicación que contiene los valores de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="defeb-107">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="defeb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="defeb-108">Remarks</span></span>  
 <span data-ttu-id="defeb-109">Un uso de **/appconfig** son escenarios avanzados en los que un ensamblado tiene que hacer referencia a la versión de .NET Framework y a la versión de .NET Framework para Silverlight de un ensamblado de referencia determinado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="defeb-109">One use of **/appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="defeb-110">Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia al escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye con Silverlight.</span><span class="sxs-lookup"><span data-stu-id="defeb-110">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="defeb-111">El mismo ensamblado del diseñador tiene que tener acceso a ambos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="defeb-111">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="defeb-112">De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="defeb-112">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="defeb-113">La opción del compilador **/appconfig** le permite especificar la ubicación de un archivo app.config que deshabilita el comportamiento predeterminado usando una etiqueta `<supportPortability>`, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="defeb-113">The **/appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="defeb-114">El compilador pasa la ubicación del archivo a la lógica de enlace del ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="defeb-114">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="defeb-115">Si está usando Microsoft Build Engine (MSBuild) para compilar su aplicación, puede establecer la opción del compilador **/appconfig** mediante la adición de una etiqueta de propiedad al archivo .csproj.</span><span class="sxs-lookup"><span data-stu-id="defeb-115">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **/appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="defeb-116">Para usar el archivo app.config que ya está establecido en el proyecto, agregue la etiqueta `<UseAppConfigForCompiler>` de propiedades al archivo .csproj y establezca su valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="defeb-116">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="defeb-117">Para especificar otro archivo app.config, agregue la etiqueta `<AppConfigForCompiler>` de propiedades y establezca su valor en la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="defeb-117">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="defeb-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="defeb-118">Example</span></span>  
 <span data-ttu-id="defeb-119">En el siguiente ejemplo se muestra un archivo app.config que permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="defeb-119">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="defeb-120">La opción del compilador **/appconfig** especifica la ubicación de este archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="defeb-120">The **/appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="defeb-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="defeb-121">See Also</span></span>  
 <span data-ttu-id="defeb-122">[Información general sobre la unificación de ensamblados de .NET Framework](http://msdn.microsoft.com/en-us/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48) </span><span class="sxs-lookup"><span data-stu-id="defeb-122">[.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/en-us/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48) </span></span>  
 <span data-ttu-id="defeb-123">[\<supportPortability> Element](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)  (Elemento <supportPortability>)</span><span class="sxs-lookup"><span data-stu-id="defeb-123">[\<supportPortability> Element](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md) </span></span>  
 [<span data-ttu-id="defeb-124">Opciones del compilador de C#, por orden alfabético</span><span class="sxs-lookup"><span data-stu-id="defeb-124">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)

