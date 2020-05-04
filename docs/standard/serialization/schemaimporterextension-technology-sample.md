---
title: Ejemplo de tecnología SchemaImporterExtension
ms.date: 03/30/2017
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
ms.openlocfilehash: d63461425fd0b3366d39892512577b0dd706de13
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490866"
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="587e0-102">Ejemplo de tecnología SchemaImporterExtension</span><span class="sxs-lookup"><span data-stu-id="587e0-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="587e0-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="587e0-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="587e0-104">En este ejemplo se muestra una clase <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> personalizada que permite el control correcto sobre la generación de código cuando se importa un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="587e0-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="587e0-105">La aplicación muestra cómo generar, registrar e invocar esta extensión.</span><span class="sxs-lookup"><span data-stu-id="587e0-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="587e0-106">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="587e0-106">To build the sample using the command prompt</span></span>  
  
1. <span data-ttu-id="587e0-107">Abra una ventana del símbolo del sistema y navegue hasta uno de los subdirectorios específicos del lenguaje para tener acceso al ejemplo.</span><span class="sxs-lookup"><span data-stu-id="587e0-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="587e0-108">Escriba **msbuild.exe OrderSchemaImporterExtension.sln** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="587e0-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="587e0-109">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="587e0-109">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="587e0-110">Abra el Explorador de archivos y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="587e0-110">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="587e0-111">Haga doble clic en el icono OrderSchemaImporterExtension.sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="587e0-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="587e0-112">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="587e0-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="587e0-113">La aplicación se generará en el directorio predeterminado \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="587e0-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="587e0-114">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="587e0-114">To run the sample</span></span>  
  
1. <span data-ttu-id="587e0-115">Navegue hasta el directorio que contiene el nuevo ejecutable, mediante el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="587e0-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2. <span data-ttu-id="587e0-116">Escriba **[exe name]** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="587e0-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="587e0-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="587e0-117">Remarks</span></span>  
 <span data-ttu-id="587e0-118">Para obtener más información sobre la creación binaria de ejemplo y los pasos del registro, vea los comentarios en los archivos de código fuente y en los archivos build.proj.</span><span class="sxs-lookup"><span data-stu-id="587e0-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="587e0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="587e0-119">See also</span></span>

- <xref:System.CodeDom.CodeCompileUnit>
- <xref:System.CodeDom.CodeNamespace>
- <xref:System.CodeDom.CodeNamespaceImport>
- <xref:Microsoft.CSharp.CSharpCodeProvider>
- <xref:System.Xml.Serialization.IXmlSerializable>
- <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>
- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- <xref:System.Web.Services.Description>
- <xref:System.Web.Services.Discovery>
- <xref:System.Xml.Serialization>
- <xref:System.Uri>
- <xref:Microsoft.VisualBasic.VBCodeProvider>
- <xref:System.Web.Services.Description.WebReference>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
