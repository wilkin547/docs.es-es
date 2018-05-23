---
title: 'Cómo: Utilizar las características de documentación XML (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 6c7e30d23868959145e8941057f1c633fe6e374e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="4e224-102">Cómo: Utilizar las características de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4e224-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="4e224-103">En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.</span><span class="sxs-lookup"><span data-stu-id="4e224-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e224-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e224-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 <span data-ttu-id="4e224-105">**// Este archivo .xml se generó con el ejemplo de código anterior.**</span><span class="sxs-lookup"><span data-stu-id="4e224-105">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="4e224-106">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="4e224-106">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="4e224-107">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="4e224-107">**\<doc>**</span></span>  
 <span data-ttu-id="4e224-108">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="4e224-108">**\<assembly>**</span></span>  
 <span data-ttu-id="4e224-109">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="4e224-109">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="4e224-110">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="4e224-110">**\</assembly>**</span></span>  
 <span data-ttu-id="4e224-111">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="4e224-111">**\<members>**</span></span>  
 <span data-ttu-id="4e224-112">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="4e224-112">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="4e224-113">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-113">**\<summary>**</span></span>  
 <span data-ttu-id="4e224-114">**La documentación de resumen de nivel de clase va aquí.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-114">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="4e224-115">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="4e224-115">**\<remarks>**</span></span>  
 <span data-ttu-id="4e224-116">**Los comentarios más largos se pueden asociar con un tipo o miembro**</span><span class="sxs-lookup"><span data-stu-id="4e224-116">**Longer comments can be associated with a type or member**</span></span>  
 <span data-ttu-id="4e224-117">**con la etiqueta remarks\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="4e224-117">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="4e224-118">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-118">**\</member>**</span></span>  
 <span data-ttu-id="4e224-119">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="4e224-119">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="4e224-120">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-120">**\<summary>**</span></span>  
 <span data-ttu-id="4e224-121">**Almacén de la propiedad name\</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-121">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="4e224-122">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-122">**\</member>**</span></span>  
 <span data-ttu-id="4e224-123">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="4e224-123">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="4e224-124">**\<summary>Constructor de clase.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-124">**\<summary>The class constructor.\</summary>**</span></span>  
 <span data-ttu-id="4e224-125">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-125">**\</member>**</span></span>  
 <span data-ttu-id="4e224-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="4e224-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="4e224-127">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-127">**\<summary>**</span></span>  
 <span data-ttu-id="4e224-128">**Descripción para SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-128">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="4e224-129">**\<param name="s"> La descripción de parámetro para s va aquí\</param>**</span><span class="sxs-lookup"><span data-stu-id="4e224-129">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="4e224-130">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="4e224-130">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="4e224-131">**Puede usar el atributo cref en cualquier etiqueta para hacer referencia a un tipo o un miembro**</span><span class="sxs-lookup"><span data-stu-id="4e224-131">**You can use the cref attribute on any tag to reference a type or member**</span></span>  
 <span data-ttu-id="4e224-132">**y el compilador comprobará que la referencia existe. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="4e224-132">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="4e224-133">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-133">**\</member>**</span></span>  
 <span data-ttu-id="4e224-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="4e224-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="4e224-135">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-135">**\<summary>**</span></span>  
 <span data-ttu-id="4e224-136">**Otro método. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-136">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="4e224-137">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="4e224-137">**\<returns>**</span></span>  
 <span data-ttu-id="4e224-138">**Los resultados devueltos se describen con la etiqueta returns.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="4e224-138">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="4e224-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="4e224-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="4e224-140">**Observe el uso del atributo cref para hacer referencia a un método específico \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="4e224-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="4e224-141">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-141">**\</member>**</span></span>  
 <span data-ttu-id="4e224-142">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="4e224-142">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="4e224-143">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-143">**\<summary>**</span></span>  
 <span data-ttu-id="4e224-144">**Punto de entrada de la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="4e224-144">**The entry point for the application.**</span></span>  
 <span data-ttu-id="4e224-145">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-145">**\</summary>**</span></span>  
 <span data-ttu-id="4e224-146">**\<param name="args"> Lista de argumentos de la línea de comandos\</param>**</span><span class="sxs-lookup"><span data-stu-id="4e224-146">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="4e224-147">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-147">**\</member>**</span></span>  
 <span data-ttu-id="4e224-148">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="4e224-148">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="4e224-149">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-149">**\<summary>**</span></span>  
 <span data-ttu-id="4e224-150">**Propiedad Name \</summary>**</span><span class="sxs-lookup"><span data-stu-id="4e224-150">**Name property \</summary>**</span></span>  
 <span data-ttu-id="4e224-151">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="4e224-151">**\<value>**</span></span>  
 <span data-ttu-id="4e224-152">**Se usa una etiqueta value para describir el valor de la propiedad\</value>**</span><span class="sxs-lookup"><span data-stu-id="4e224-152">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="4e224-153">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="4e224-153">**\</member>**</span></span>  
 <span data-ttu-id="4e224-154">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="4e224-154">**\</members>**</span></span>  
<span data-ttu-id="4e224-155">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="4e224-155">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="4e224-156">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4e224-156">Compiling the Code</span></span>  
 <span data-ttu-id="4e224-157">Para compilar el ejemplo, escriba la siguiente línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="4e224-157">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="4e224-158">Esto creará el archivo XML XMLsample.xml, que se puede ver en el explorador o mediante el comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="4e224-158">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e224-159">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4e224-159">Robust Programming</span></span>  
 <span data-ttu-id="4e224-160">La documentación XML empieza con ///.</span><span class="sxs-lookup"><span data-stu-id="4e224-160">XML documentation starts with ///.</span></span> <span data-ttu-id="4e224-161">Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///.</span><span class="sxs-lookup"><span data-stu-id="4e224-161">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="4e224-162">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="4e224-162">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="4e224-163">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="4e224-163">The documentation must be well-formed XML.</span></span> <span data-ttu-id="4e224-164">Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.</span><span class="sxs-lookup"><span data-stu-id="4e224-164">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="4e224-165">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="4e224-165">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="4e224-166">pero hay un conjunto de etiquetas recomendado (vea la sección con información adicional).</span><span class="sxs-lookup"><span data-stu-id="4e224-166">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="4e224-167">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="4e224-167">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="4e224-168">La etiqueta \<param> se usa para describir parámetros.</span><span class="sxs-lookup"><span data-stu-id="4e224-168">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="4e224-169">Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="4e224-169">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="4e224-170">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="4e224-170">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="4e224-171">El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="4e224-171">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="4e224-172">El compilador comprobará si existe ese elemento de código.</span><span class="sxs-lookup"><span data-stu-id="4e224-172">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="4e224-173">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="4e224-173">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="4e224-174">El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="4e224-174">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="4e224-175">IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="4e224-175">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4e224-176">El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos).</span><span class="sxs-lookup"><span data-stu-id="4e224-176">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="4e224-177">Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.</span><span class="sxs-lookup"><span data-stu-id="4e224-177">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e224-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e224-178">See Also</span></span>  
 [<span data-ttu-id="4e224-179">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4e224-179">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4e224-180">/doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4e224-180">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="4e224-181">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="4e224-181">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
