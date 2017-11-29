---
title: "Ejemplo de tecnología SchemaImporterExtension"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68e89053d1d4a36a0f015ed4e0082ae88e1de6a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="77af9-102">Ejemplo de tecnología SchemaImporterExtension</span><span class="sxs-lookup"><span data-stu-id="77af9-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="77af9-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="77af9-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="77af9-104">En este ejemplo se muestra una clase <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> personalizada que permite el control correcto sobre la generación de código cuando se importa un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="77af9-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="77af9-105">La aplicación muestra cómo generar, registrar e invocar esta extensión.</span><span class="sxs-lookup"><span data-stu-id="77af9-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="77af9-106">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="77af9-106">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="77af9-107">Abra una ventana del símbolo del sistema y navegue hasta uno de los subdirectorios específicos del lenguaje para tener acceso al ejemplo.</span><span class="sxs-lookup"><span data-stu-id="77af9-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="77af9-108">Escriba **msbuild.exe OrderSchemaImporterExtension.sln** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="77af9-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="77af9-109">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="77af9-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="77af9-110">Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="77af9-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="77af9-111">Haga doble clic en el icono OrderSchemaImporterExtension.sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77af9-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="77af9-112">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="77af9-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="77af9-113">La aplicación se generará en el directorio predeterminado \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="77af9-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="77af9-114">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="77af9-114">To run the sample</span></span>  
  
1.  <span data-ttu-id="77af9-115">Navegue hasta el directorio que contiene el nuevo ejecutable, mediante el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="77af9-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2.  <span data-ttu-id="77af9-116">Escriba **[exe name]** en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="77af9-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77af9-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77af9-117">Remarks</span></span>  
 <span data-ttu-id="77af9-118">Para obtener más información sobre la creación binaria de ejemplo y los pasos del registro, vea los comentarios en los archivos de código fuente y en los archivos build.proj.</span><span class="sxs-lookup"><span data-stu-id="77af9-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77af9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="77af9-119">See Also</span></span>  
 <xref:System.CodeDom.CodeCompileUnit>  
 <xref:System.CodeDom.CodeNamespace>  
 <xref:System.CodeDom.CodeNamespaceImport>  
 <xref:Microsoft.CSharp.CSharpCodeProvider>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>  
 <xref:System.CodeDom>  
 <xref:System.CodeDom.Compiler>  
 <xref:System.Web.Services.Description>  
 <xref:System.Web.Services.Discovery>  
 <xref:System.Xml.Serialization>  
 <xref:System.Uri>  
 <xref:Microsoft.VisualBasic.VBCodeProvider>  
 <xref:System.Web.Services.Description.WebReference>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>
