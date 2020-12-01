---
title: Mgmtclassgen.exe (Generador de clases fuertemente tipadas para administración)
description: Conozca Mgmtclassgen.exe, el Generador de clases fuertemente tipadas para administración. Esta herramienta le permite generar rápidamente una clase administrada enlazada en tiempo de compilación para una clase WMI.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CIM types
- Management Strongly Typed Class Generator
- WMI class
- Mgmtclassgen.exe
- early-bound managed classes
ms.assetid: 02ce6699-49b5-4a0b-b0d5-1003c491232e
ms.openlocfilehash: 1dea4b0b94053919169abb639ff48ecd3abbd66c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279160"
---
# <a name="mgmtclassgenexe-management-strongly-typed-class-generator"></a><span data-ttu-id="1060d-104">Mgmtclassgen.exe (Generador de clases fuertemente tipadas para administración)</span><span class="sxs-lookup"><span data-stu-id="1060d-104">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>

<span data-ttu-id="1060d-105">La herramienta Generador de clases fuertemente tipadas para administración permite generar con rapidez una clase administrada en tiempo de compilación para una clase especificada de Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="1060d-105">The Management Strongly Typed Class Generator tool enables you to quickly generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span> <span data-ttu-id="1060d-106">La clase generada simplifica el código que se debe escribir para tener acceso a una instancia de la clase de WMI.</span><span class="sxs-lookup"><span data-stu-id="1060d-106">The generated class simplifies the code you must write to access an instance of the WMI class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1060d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1060d-107">Syntax</span></span>  
  
```console  
mgmtclassgen
WMIClass [options]
```  
  
|<span data-ttu-id="1060d-108">Argumento</span><span class="sxs-lookup"><span data-stu-id="1060d-108">Argument</span></span>|<span data-ttu-id="1060d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1060d-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1060d-110">*WMIClass*</span><span class="sxs-lookup"><span data-stu-id="1060d-110">*WMIClass*</span></span>|<span data-ttu-id="1060d-111">Clase de Instrumental de administración de Windows para la que se genera una clase administrada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1060d-111">The Windows Management Instrumentation class for which to generate an early-bound managed class.</span></span>|  
  
|<span data-ttu-id="1060d-112">Opción</span><span class="sxs-lookup"><span data-stu-id="1060d-112">Option</span></span>|<span data-ttu-id="1060d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1060d-113">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1060d-114">**/l**  *language*</span><span class="sxs-lookup"><span data-stu-id="1060d-114">**/l**  *language*</span></span>|<span data-ttu-id="1060d-115">Especifica el lenguaje en el que se genera la clase administrada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="1060d-115">Specifies the language in which to generate the early-bound managed class.</span></span> <span data-ttu-id="1060d-116">Puede especificar **CS** (C#, predeterminado), **VB** (Visual Basic), **MC** (C++) o **JS** (JScript) como argumento del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="1060d-116">You can specify **CS** (C#; default), **VB** (Visual Basic),  **MC** (C++), or **JS** (JScript) as the language argument.</span></span>|  
|<span data-ttu-id="1060d-117">**/m**  *machine*</span><span class="sxs-lookup"><span data-stu-id="1060d-117">**/m**  *machine*</span></span>|<span data-ttu-id="1060d-118">Especifica el equipo con el que se va a conectar y en el que reside la clase de WMI.</span><span class="sxs-lookup"><span data-stu-id="1060d-118">Specifies the computer to connect to, where the WMI class resides.</span></span> <span data-ttu-id="1060d-119">La opción predeterminada es el equipo local.</span><span class="sxs-lookup"><span data-stu-id="1060d-119">The default is the local computer.</span></span>|  
|<span data-ttu-id="1060d-120">**/n**  *path*</span><span class="sxs-lookup"><span data-stu-id="1060d-120">**/n**  *path*</span></span>|<span data-ttu-id="1060d-121">Especifica la ruta de acceso al espacio de nombres de WMI que contiene la clase de WMI.</span><span class="sxs-lookup"><span data-stu-id="1060d-121">Specifies the path to the WMI namespace that contains the WMI class.</span></span> <span data-ttu-id="1060d-122">Si no se especifica esta opción, la herramienta genera código para *WMIClass* en el espacio de nombres **Root\cimv2** predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1060d-122">If you do not specify this option, the tool generates code for *WMIClass* in the default **Root\cimv2** namespace.</span></span>|  
|<span data-ttu-id="1060d-123">**/o**  *classnamespace*</span><span class="sxs-lookup"><span data-stu-id="1060d-123">**/o**  *classnamespace*</span></span>|<span data-ttu-id="1060d-124">Especifica el espacio de nombres de .NET en el que se genera la clase de código administrado.</span><span class="sxs-lookup"><span data-stu-id="1060d-124">Specifies the .NET namespace in which to generate the managed code class.</span></span> <span data-ttu-id="1060d-125">Si no se especifica esta opción, la herramienta genera el espacio de nombres utilizando el espacio de nombres de WMI y el prefijo de esquema.</span><span class="sxs-lookup"><span data-stu-id="1060d-125">If you do not specify this option, the tool generates the namespace using the WMI namespace and the schema prefix.</span></span> <span data-ttu-id="1060d-126">El prefijo de esquema es la parte del nombre de clase que figura delante del carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="1060d-126">The schema prefix is the part of the class name preceding the underscore character.</span></span> <span data-ttu-id="1060d-127">Por ejemplo, para la clase **Win32_OperatingSystem** del espacio de nombres **Root\cimv2**, la herramienta generaría la clase en **ROOT.CIMV2.Win32**.</span><span class="sxs-lookup"><span data-stu-id="1060d-127">For example, for the **Win32_OperatingSystem** class in the **Root\cimv2** namespace, the tool would generate the class in **ROOT.CIMV2.Win32**.</span></span>|  
|<span data-ttu-id="1060d-128">**/p**  *filepath*</span><span class="sxs-lookup"><span data-stu-id="1060d-128">**/p**  *filepath*</span></span>|<span data-ttu-id="1060d-129">Especifica la ruta de acceso al archivo donde se guarda el código generado.</span><span class="sxs-lookup"><span data-stu-id="1060d-129">Specifies the path to the file in which to save the generated code.</span></span> <span data-ttu-id="1060d-130">Si no se especifica esta opción, la herramienta crea el archivo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="1060d-130">If you do not specify this option, the tool creates the file in the current directory.</span></span> <span data-ttu-id="1060d-131">Asigna un nombre a la clase y al archivo donde se genera la clase mediante el argumento *WMIClass*.</span><span class="sxs-lookup"><span data-stu-id="1060d-131">It names the class and file in which it generates the class using the *WMIClass* argument.</span></span> <span data-ttu-id="1060d-132">El nombre de la clase y el nombre del archivo coinciden con el nombre de *WMIClass*.</span><span class="sxs-lookup"><span data-stu-id="1060d-132">The name of the class and the file are the same as the name of the *WMIClass.*</span></span> <span data-ttu-id="1060d-133">Si *WMIClass* contiene un carácter de subrayado, la herramienta usa la parte del nombre de clase que figura detrás del carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="1060d-133">If *WMIClass* contains an underscore character, the tool uses the part of the class name following the underscore character.</span></span> <span data-ttu-id="1060d-134">Por ejemplo, si el nombre de *WMIClass* tiene el formato **Win32_LogicalDisk**, el nombre de la clase generada y del archivo es "logicaldisk".</span><span class="sxs-lookup"><span data-stu-id="1060d-134">For example, if the *WMIClass* name is in the format **Win32_LogicalDisk**, the generated class and file is named "logicaldisk".</span></span> <span data-ttu-id="1060d-135">Si ya existe un archivo, la herramienta sobrescribe el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="1060d-135">If a file already exists, the tool overwrites the existing file.</span></span>|  
|<span data-ttu-id="1060d-136">**/pw**  *password*</span><span class="sxs-lookup"><span data-stu-id="1060d-136">**/pw**  *password*</span></span>|<span data-ttu-id="1060d-137">Especifica la contraseña que se usa al iniciar sesión en el equipo especificado con la opción **/m**.</span><span class="sxs-lookup"><span data-stu-id="1060d-137">Specifies the password to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="1060d-138">**/u**  *user name*</span><span class="sxs-lookup"><span data-stu-id="1060d-138">**/u**  *user name*</span></span>|<span data-ttu-id="1060d-139">Especifica el nombre de usuario que se usa al iniciar sesión en el equipo especificado con la opción **/m**.</span><span class="sxs-lookup"><span data-stu-id="1060d-139">Specifies the user name to use when logging on to a computer specified by the **/m** option.</span></span>|  
|<span data-ttu-id="1060d-140">**/?**</span><span class="sxs-lookup"><span data-stu-id="1060d-140">**/?**</span></span>|<span data-ttu-id="1060d-141">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="1060d-141">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1060d-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1060d-142">Remarks</span></span>  

 <span data-ttu-id="1060d-143">Mgmtclassgen.exe usa el método <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1060d-143">Mgmtclassgen.exe uses the <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1060d-144">Por tanto, se puede utilizar cualquier proveedor de código personalizado para generar código en lenguajes administrados distintos de C#, Visual Basic y JScript.</span><span class="sxs-lookup"><span data-stu-id="1060d-144">Therefore, you can use any custom code provider to generate code in managed languages other than C#, Visual Basic, and JScript.</span></span>  
  
 <span data-ttu-id="1060d-145">Tenga en cuenta que las clases generadas se enlazan al esquema para el que se generan.</span><span class="sxs-lookup"><span data-stu-id="1060d-145">Note that generated classes are bound to the schema for which they are generated.</span></span> <span data-ttu-id="1060d-146">Si el esquema subyacente cambia, se debe volver a generar la clase para que los cambios se reflejen en el esquema.</span><span class="sxs-lookup"><span data-stu-id="1060d-146">If the underlying schema changes, you must regenerate the class if you want it to reflect changes to the schema.</span></span>  
  
 <span data-ttu-id="1060d-147">La tabla siguiente muestra cómo se asignan los tipos del Modelo de información común (CIM) de WMI a los tipos de datos en una clase generada:</span><span class="sxs-lookup"><span data-stu-id="1060d-147">The following table shows how WMI Common Information Model (CIM) types map to data types in a generated class:</span></span>  
  
|<span data-ttu-id="1060d-148">Tipo de CIM</span><span class="sxs-lookup"><span data-stu-id="1060d-148">CIM type</span></span>|<span data-ttu-id="1060d-149">Tipo de datos en la clase generada</span><span class="sxs-lookup"><span data-stu-id="1060d-149">Data type in the generated class</span></span>|  
|--------------|--------------------------------------|  
|<span data-ttu-id="1060d-150">CIM_SINT8</span><span class="sxs-lookup"><span data-stu-id="1060d-150">CIM_SINT8</span></span>|<span data-ttu-id="1060d-151">**SByte**</span><span class="sxs-lookup"><span data-stu-id="1060d-151">**SByte**</span></span>|  
|<span data-ttu-id="1060d-152">CIM_UINT8</span><span class="sxs-lookup"><span data-stu-id="1060d-152">CIM_UINT8</span></span>|<span data-ttu-id="1060d-153">**Byte**</span><span class="sxs-lookup"><span data-stu-id="1060d-153">**Byte**</span></span>|  
|<span data-ttu-id="1060d-154">CIM_SINT16</span><span class="sxs-lookup"><span data-stu-id="1060d-154">CIM_SINT16</span></span>|<span data-ttu-id="1060d-155">**Int16**</span><span class="sxs-lookup"><span data-stu-id="1060d-155">**Int16**</span></span>|  
|<span data-ttu-id="1060d-156">CIM_UINT16</span><span class="sxs-lookup"><span data-stu-id="1060d-156">CIM_UINT16</span></span>|<span data-ttu-id="1060d-157">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="1060d-157">**UInt16**</span></span>|  
|<span data-ttu-id="1060d-158">CIM_SINT32</span><span class="sxs-lookup"><span data-stu-id="1060d-158">CIM_SINT32</span></span>|<span data-ttu-id="1060d-159">**Int32**</span><span class="sxs-lookup"><span data-stu-id="1060d-159">**Int32**</span></span>|  
|<span data-ttu-id="1060d-160">SIM_UINT32</span><span class="sxs-lookup"><span data-stu-id="1060d-160">SIM_UINT32</span></span>|<span data-ttu-id="1060d-161">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="1060d-161">**UInt32**</span></span>|  
|<span data-ttu-id="1060d-162">CIM_SINT64</span><span class="sxs-lookup"><span data-stu-id="1060d-162">CIM_SINT64</span></span>|<span data-ttu-id="1060d-163">**Int64**</span><span class="sxs-lookup"><span data-stu-id="1060d-163">**Int64**</span></span>|  
|<span data-ttu-id="1060d-164">CIM_UINT64</span><span class="sxs-lookup"><span data-stu-id="1060d-164">CIM_UINT64</span></span>|<span data-ttu-id="1060d-165">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="1060d-165">**UInt64**</span></span>|  
|<span data-ttu-id="1060d-166">CIM_REAL32</span><span class="sxs-lookup"><span data-stu-id="1060d-166">CIM_REAL32</span></span>|<span data-ttu-id="1060d-167">**Single**</span><span class="sxs-lookup"><span data-stu-id="1060d-167">**Single**</span></span>|  
|<span data-ttu-id="1060d-168">CIM_REAL64</span><span class="sxs-lookup"><span data-stu-id="1060d-168">CIM_REAL64</span></span>|<span data-ttu-id="1060d-169">**Double**</span><span class="sxs-lookup"><span data-stu-id="1060d-169">**Double**</span></span>|  
|<span data-ttu-id="1060d-170">CIM_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1060d-170">CIM_BOOLEAN</span></span>|<span data-ttu-id="1060d-171">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="1060d-171">**Boolean**</span></span>|  
|<span data-ttu-id="1060d-172">CIM_String</span><span class="sxs-lookup"><span data-stu-id="1060d-172">CIM_String</span></span>|<span data-ttu-id="1060d-173">**String**</span><span class="sxs-lookup"><span data-stu-id="1060d-173">**String**</span></span>|  
|<span data-ttu-id="1060d-174">CIM_DATETIME</span><span class="sxs-lookup"><span data-stu-id="1060d-174">CIM_DATETIME</span></span>|<span data-ttu-id="1060d-175">**DateTime** o **TimeSpan**</span><span class="sxs-lookup"><span data-stu-id="1060d-175">**DateTime** or **TimeSpan**</span></span>|  
|<span data-ttu-id="1060d-176">CIM_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="1060d-176">CIM_REFERENCE</span></span>|<span data-ttu-id="1060d-177">**ManagementPath**</span><span class="sxs-lookup"><span data-stu-id="1060d-177">**ManagementPath**</span></span>|  
|<span data-ttu-id="1060d-178">CIM_CHAR16</span><span class="sxs-lookup"><span data-stu-id="1060d-178">CIM_CHAR16</span></span>|<span data-ttu-id="1060d-179">**Char**</span><span class="sxs-lookup"><span data-stu-id="1060d-179">**Char**</span></span>|  
|<span data-ttu-id="1060d-180">CIM_OBJECT</span><span class="sxs-lookup"><span data-stu-id="1060d-180">CIM_OBJECT</span></span>|<span data-ttu-id="1060d-181">**ManagementBaseObject**</span><span class="sxs-lookup"><span data-stu-id="1060d-181">**ManagementBaseObject**</span></span>|  
|<span data-ttu-id="1060d-182">CIM_IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="1060d-182">CIM_IUNKNOWN</span></span>|<span data-ttu-id="1060d-183">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="1060d-183">**Object**</span></span>|  
|<span data-ttu-id="1060d-184">CIM_ARRAY</span><span class="sxs-lookup"><span data-stu-id="1060d-184">CIM_ARRAY</span></span>|<span data-ttu-id="1060d-185">Matriz de los objetos mencionados anteriormente</span><span class="sxs-lookup"><span data-stu-id="1060d-185">Array of the above mentioned objects</span></span>|  
  
 <span data-ttu-id="1060d-186">Tenga en cuenta los comportamientos siguientes cuando se genera una clase WMI:</span><span class="sxs-lookup"><span data-stu-id="1060d-186">Note the following behaviors when you generate a WMI class:</span></span>  
  
- <span data-ttu-id="1060d-187">Es posible que un método o una propiedad públicos estándar tengan el mismo nombre que un método o una propiedad existentes.</span><span class="sxs-lookup"><span data-stu-id="1060d-187">It is possible for a standard public property or method to have the same name as an existing property or method.</span></span> <span data-ttu-id="1060d-188">Si esto sucede, la herramienta cambia el nombre del método o de la propiedad en la clase generada para evitar conflictos de nombres.</span><span class="sxs-lookup"><span data-stu-id="1060d-188">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="1060d-189">Es posible que el nombre de un método o de una propiedad en una clase generada sea una palabra clave en el lenguaje de programación de destino.</span><span class="sxs-lookup"><span data-stu-id="1060d-189">It is possible for the name of a property or method in a generated class to be a keyword in the target programming language.</span></span> <span data-ttu-id="1060d-190">Si esto sucede, la herramienta cambia el nombre del método o de la propiedad en la clase generada para evitar conflictos de nombres.</span><span class="sxs-lookup"><span data-stu-id="1060d-190">If this occurs, the tool changes the name of the property or method in the generated class to avoid naming conflicts.</span></span>  
  
- <span data-ttu-id="1060d-191">En WMI, los calificadores son modificadores que contienen información para describir una clase, una instancia, una propiedad o un método.</span><span class="sxs-lookup"><span data-stu-id="1060d-191">In WMI, qualifiers are modifiers that contain information to describe a class, instance, property, or method.</span></span> <span data-ttu-id="1060d-192">WMI usa calificadores estándar como **Read**, **Write** y **Key** para describir una propiedad en una clase generada.</span><span class="sxs-lookup"><span data-stu-id="1060d-192">WMI uses standard qualifiers such as **Read**, **Write**, and **Key** to describe a property in a generated class.</span></span> <span data-ttu-id="1060d-193">Por ejemplo, una propiedad que se modifica con un calificador **Read** se define únicamente con un descriptor de acceso **get** de propiedad en la clase generada.</span><span class="sxs-lookup"><span data-stu-id="1060d-193">For example, a property that is modified with a **Read** qualifier is defined only with a property **get** accessor in the generated class.</span></span> <span data-ttu-id="1060d-194">Como las propiedades marcadas con el calificador **Read** están diseñadas para ser de solo lectura, no se define ningún descriptor de acceso **set**.</span><span class="sxs-lookup"><span data-stu-id="1060d-194">Because a property marked with the **Read** qualifier is intended to be read-only, a **set** accessor is not defined.</span></span>  
  
- <span data-ttu-id="1060d-195">Una propiedad numérica se puede modificar mediante los calificadores **Values** y **ValueMaps** para indicar que la propiedad solo se puede establecer en valores permisibles especificados.</span><span class="sxs-lookup"><span data-stu-id="1060d-195">A numeric property can be modified by the **Values** and **ValueMaps** qualifiers to indicate that the property can be set only to specified permissible values.</span></span> <span data-ttu-id="1060d-196">Con estos calificadores **Values** y **ValueMaps** se genera una enumeración y se asigna la propiedad a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="1060d-196">An enumeration is generated with these **Values** and **ValueMaps** and the property is mapped to the enumeration.</span></span>  
  
- <span data-ttu-id="1060d-197">WMI utiliza el término singleton para describir una clase que solo puede tener una instancia.</span><span class="sxs-lookup"><span data-stu-id="1060d-197">The WMI uses the term singleton to describe a class that can have only one instance.</span></span> <span data-ttu-id="1060d-198">Por tanto, el constructor sin parámetros para una clase singleton inicializará la clase en la única instancia de la misma.</span><span class="sxs-lookup"><span data-stu-id="1060d-198">Therefore, the parameterless constructor for a singleton class will initialize the class to the only instance of the class.</span></span>  
  
- <span data-ttu-id="1060d-199">Una clase WMI puede tener propiedades que sean objetos.</span><span class="sxs-lookup"><span data-stu-id="1060d-199">A WMI class can have properties that are objects.</span></span> <span data-ttu-id="1060d-200">Cuando se genera una clase fuertemente tipada para este tipo de clase WMI, se debe considerar la posibilidad de generar clases fuertemente tipadas para los tipos de las propiedades de objetos insertados.</span><span class="sxs-lookup"><span data-stu-id="1060d-200">When you generate a strongly typed class for this type of WMI class, you should consider generating strongly typed classes for the types of the embedded object properties.</span></span> <span data-ttu-id="1060d-201">Esto permitirá acceder a los objetos insertados de un modo fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="1060d-201">This will allow you to access the embedded objects in a strongly typed manner.</span></span> <span data-ttu-id="1060d-202">Tenga en cuenta que existe la posibilidad de que el código generado no pueda detectar el tipo del objeto incrustado.</span><span class="sxs-lookup"><span data-stu-id="1060d-202">Note that the generated code might not be able to detect the type of the embedded object.</span></span> <span data-ttu-id="1060d-203">En este caso, se creará un comentario en el código generado para informar al usuario de este punto.</span><span class="sxs-lookup"><span data-stu-id="1060d-203">In this case, a comment will be created in the generated code to notify you of this issue.</span></span> <span data-ttu-id="1060d-204">A continuación, se puede modificar el código generado para que el tipo de la propiedad corresponda a la otra clase generada.</span><span class="sxs-lookup"><span data-stu-id="1060d-204">You can then modify the generated code to type the property to the other generated class.</span></span>  
  
- <span data-ttu-id="1060d-205">En WMI, el valor de los datos del tipo de datos CIM_DATETIME puede representar una fecha y hora específicas o un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="1060d-205">In WMI, the data value of the CIM_DATETIME data type can represent either a specific date and time or a time interval.</span></span> <span data-ttu-id="1060d-206">Si el valor de los datos representa una fecha y hora, el tipo de datos de la clase generada es **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="1060d-206">If the data value represents a date and time, the data type in the generated class is **DateTime**.</span></span> <span data-ttu-id="1060d-207">Si el valor de los datos representa un intervalo de tiempo, el tipo de datos de la clase generada es **TimeSpan**.</span><span class="sxs-lookup"><span data-stu-id="1060d-207">If the data value represents a time interval, the data type in the generated class is **TimeSpan**.</span></span>  
  
 <span data-ttu-id="1060d-208">Otra posibilidad consiste en generar una clase fuertemente tipada mediante la extensión de administración del explorador de servidores en Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="1060d-208">You can alternately generate a strongly typed class using the Server Explorer Management Extension in Visual Studio .NET.</span></span>  
  
 <span data-ttu-id="1060d-209">Para obtener más información sobre WMI, vea el tema sobre **Instrumental de administración de Windows** en la documentación de Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="1060d-209">For more information about WMI, see the **Windows Management Instrumentation** topic in the Platform SDK documentation.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1060d-210">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1060d-210">Examples</span></span>  

 <span data-ttu-id="1060d-211">El siguiente comando genera una clase administrada en código de C# para la clase WMI **Win32_LogicalDisk** en el espacio de nombres **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="1060d-211">The following command generates a managed class in C# code for the **Win32_LogicalDisk** WMI class in the **Root\cimv2** namespace.</span></span> <span data-ttu-id="1060d-212">La herramienta escribe la clase administrada en el archivo de código fuente en c:\disk.cs en el espacio de nombres **ROOT.CIMV2.Win32**.</span><span class="sxs-lookup"><span data-stu-id="1060d-212">The tool writes the managed class to the source file at c:\disk.cs in the **ROOT.CIMV2.Win32** namespace.</span></span>  
  
```console  
mgmtclassgen Win32_LogicalDisk /n root\cimv2 /l CS /p c:\disk.cs  
```  
  
 <span data-ttu-id="1060d-213">En el ejemplo de código siguiente se muestra la forma de utilizar mediante programación una clase generada.</span><span class="sxs-lookup"><span data-stu-id="1060d-213">The following code example shows how to use a generated class programmatically.</span></span> <span data-ttu-id="1060d-214">En primer lugar, se enumera una instancia de la clase y se imprime la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1060d-214">First, an instance of the class is enumerated and the path is printed.</span></span> <span data-ttu-id="1060d-215">A continuación, se crea una instancia de la clase generada que se va a inicializar con una instancia de WMI.</span><span class="sxs-lookup"><span data-stu-id="1060d-215">Next, an instance of the generated class to be initialized is created with an instance of WMI.</span></span> <span data-ttu-id="1060d-216">`Process` es la clase generada para **Win32_Process** y `LogicalDisk` es la clase generada para **Win32_LogicalDisk** en el espacio de nombres **Root\cimv2**.</span><span class="sxs-lookup"><span data-stu-id="1060d-216">`Process` is the class generated for **Win32_Process** and `LogicalDisk` is the class generated for **Win32_LogicalDisk** in the **Root\cimv2** namespace.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports ROOT.CIMV2.Win32  
  
Public Class App
   Public Shared Sub Main()
      ' Enumerate instances of the Win32_process.  
      ' Print the Name property of the instance.  
      Dim ps As Process
      For Each ps In  Process.GetInstances()  
         Console.WriteLine(ps.Name)  
      Next ps  
  
      ' Initialize the instance of LogicalDisk with  
      ' the WMI instance pointing to logical drive d:.  
      Dim dskD As New LogicalDisk(New _  
         ManagementPath("win32_LogicalDisk.DeviceId=""d:"""))  
      Console.WriteLine(dskD.Caption)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Management;  
using ROOT.CIMV2.Win32;  
  
public class App  
{  
   public static void Main()  
   {  
      // Enumerate instances of the Win32_process.  
      // Print the Name property of the instance.  
      foreach(Process ps in Process.GetInstances())  
      {  
         Console.WriteLine(ps.Name);  
      }  
  
      // Initialize the instance of LogicalDisk with  
      // the WMI instance pointing to logical drive d:.  
      LogicalDisk dskD = new LogicalDisk(new ManagementPath(  
        "win32_LogicalDisk.DeviceId=\"d:\""));  
      Console.WriteLine(dskD.Caption);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1060d-217">Vea también</span><span class="sxs-lookup"><span data-stu-id="1060d-217">See also</span></span>

- <xref:System.Management>
- <xref:System.Management.ManagementClass.GetStronglyTypedClassCode%2A?displayProperty=nameWithType>
- <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>
- [<span data-ttu-id="1060d-218">Herramientas</span><span class="sxs-lookup"><span data-stu-id="1060d-218">Tools</span></span>](index.md)
- [<span data-ttu-id="1060d-219">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="1060d-219">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
