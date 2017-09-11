---
title: "Cómo: Utilizar las características de documentación XML (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
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
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="53e52-102">Cómo: Utilizar las características de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="53e52-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="53e52-103">En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.</span><span class="sxs-lookup"><span data-stu-id="53e52-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53e52-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53e52-104">Example</span></span>  
 <span data-ttu-id="53e52-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="53e52-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span></span>  
  
 <span data-ttu-id="53e52-106">**// Este archivo .xml se generó con el ejemplo de código anterior.**</span><span class="sxs-lookup"><span data-stu-id="53e52-106">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="53e52-107">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="53e52-107">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="53e52-108">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="53e52-108">**\<doc>**</span></span>  
 <span data-ttu-id="53e52-109">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="53e52-109">**\<assembly>**</span></span>  
 <span data-ttu-id="53e52-110">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="53e52-110">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="53e52-111">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="53e52-111">**\</assembly>**</span></span>  
 <span data-ttu-id="53e52-112">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="53e52-112">**\<members>**</span></span>  
 <span data-ttu-id="53e52-113">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="53e52-113">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="53e52-114">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-114">**\<summary>**</span></span>  
 <span data-ttu-id="53e52-115">**La documentación de resumen de nivel de clase va aquí.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-115">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="53e52-116">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="53e52-116">**\<remarks>**</span></span>  
 <span data-ttu-id="53e52-117">**Los comentarios más largos se pueden asociar con un tipo o miembro** </span><span class="sxs-lookup"><span data-stu-id="53e52-117">**Longer comments can be associated with a type or member** </span></span>  
 <span data-ttu-id="53e52-118">**con la etiqueta remarks\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="53e52-118">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="53e52-119">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-119">**\</member>**</span></span>  
 <span data-ttu-id="53e52-120">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="53e52-120">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="53e52-121">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-121">**\<summary>**</span></span>  
 <span data-ttu-id="53e52-122">**Almacén de la propiedad name\</summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-122">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="53e52-123">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-123">**\</member>**</span></span>  
 <span data-ttu-id="53e52-124">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="53e52-124">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="53e52-125">**\<summary>Constructor de clase.\</summary>** </span><span class="sxs-lookup"><span data-stu-id="53e52-125">**\<summary>The class constructor.\</summary>** </span></span>  
 <span data-ttu-id="53e52-126">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-126">**\</member>**</span></span>  
 <span data-ttu-id="53e52-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="53e52-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="53e52-128">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-128">**\<summary>**</span></span>  
 <span data-ttu-id="53e52-129">**Descripción para SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-129">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="53e52-130">**\<param name="s"> La descripción de parámetro para s va aquí\</param>**</span><span class="sxs-lookup"><span data-stu-id="53e52-130">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="53e52-131">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="53e52-131">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="53e52-132">**Puede usar el atributo cref en cualquier etiqueta para hacer referencia a un tipo o un miembro** </span><span class="sxs-lookup"><span data-stu-id="53e52-132">**You can use the cref attribute on any tag to reference a type or member** </span></span>  
 <span data-ttu-id="53e52-133">**y el compilador comprobará que la referencia existe. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="53e52-133">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="53e52-134">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-134">**\</member>**</span></span>  
 <span data-ttu-id="53e52-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="53e52-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="53e52-136">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-136">**\<summary>**</span></span>  
 <span data-ttu-id="53e52-137">**Otro método. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-137">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="53e52-138">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="53e52-138">**\<returns>**</span></span>  
 <span data-ttu-id="53e52-139">**Los resultados devueltos se describen con la etiqueta returns.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="53e52-139">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="53e52-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="53e52-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="53e52-141">**Observe el uso del atributo cref para hacer referencia a un método específico \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="53e52-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="53e52-142">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-142">**\</member>**</span></span>  
 <span data-ttu-id="53e52-143">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="53e52-143">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="53e52-144">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-144">**\<summary>**</span></span>  
 <span data-ttu-id="53e52-145">**Punto de entrada de la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="53e52-145">**The entry point for the application.**</span></span>  
 <span data-ttu-id="53e52-146">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-146">**\</summary>**</span></span>  
 <span data-ttu-id="53e52-147">**\<param name="args"> Lista de argumentos de la línea de comandos\</param>**</span><span class="sxs-lookup"><span data-stu-id="53e52-147">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="53e52-148">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-148">**\</member>**</span></span>  
 <span data-ttu-id="53e52-149">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="53e52-149">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="53e52-150">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-150">**\<summary>**</span></span>  
 <span data-ttu-id="53e52-151">**Propiedad Name \</summary>**</span><span class="sxs-lookup"><span data-stu-id="53e52-151">**Name property \</summary>**</span></span>  
 <span data-ttu-id="53e52-152">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="53e52-152">**\<value>**</span></span>  
 <span data-ttu-id="53e52-153">**Se usa una etiqueta value para describir el valor de la propiedad\</value>**</span><span class="sxs-lookup"><span data-stu-id="53e52-153">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="53e52-154">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="53e52-154">**\</member>**</span></span>  
 <span data-ttu-id="53e52-155">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="53e52-155">**\</members>**</span></span>  
<span data-ttu-id="53e52-156">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="53e52-156">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="53e52-157">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="53e52-157">Compiling the Code</span></span>  
 <span data-ttu-id="53e52-158">Para compilar el ejemplo, escriba la siguiente línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="53e52-158">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="53e52-159">Esto creará el archivo XML XMLsample.xml, que se puede ver en el explorador o mediante el comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="53e52-159">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="53e52-160">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="53e52-160">Robust Programming</span></span>  
 <span data-ttu-id="53e52-161">La documentación XML empieza con ///.</span><span class="sxs-lookup"><span data-stu-id="53e52-161">XML documentation starts with ///.</span></span> <span data-ttu-id="53e52-162">Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///.</span><span class="sxs-lookup"><span data-stu-id="53e52-162">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="53e52-163">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="53e52-163">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="53e52-164">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="53e52-164">The documentation must be well-formed XML.</span></span> <span data-ttu-id="53e52-165">Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.</span><span class="sxs-lookup"><span data-stu-id="53e52-165">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="53e52-166">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="53e52-166">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="53e52-167">pero hay un conjunto de etiquetas recomendado (vea la sección con información adicional).</span><span class="sxs-lookup"><span data-stu-id="53e52-167">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="53e52-168">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="53e52-168">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="53e52-169">La etiqueta \<param> se usa para describir parámetros.</span><span class="sxs-lookup"><span data-stu-id="53e52-169">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="53e52-170">Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="53e52-170">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="53e52-171">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="53e52-171">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="53e52-172">El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="53e52-172">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="53e52-173">El compilador comprobará si existe ese elemento de código.</span><span class="sxs-lookup"><span data-stu-id="53e52-173">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="53e52-174">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="53e52-174">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="53e52-175">El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="53e52-175">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="53e52-176">IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="53e52-176">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53e52-177">El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos).</span><span class="sxs-lookup"><span data-stu-id="53e52-177">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="53e52-178">Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.</span><span class="sxs-lookup"><span data-stu-id="53e52-178">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e52-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="53e52-179">See Also</span></span>  
 <span data-ttu-id="53e52-180">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="53e52-180">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="53e52-181">[/doc (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="53e52-181">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="53e52-182">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="53e52-182">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

