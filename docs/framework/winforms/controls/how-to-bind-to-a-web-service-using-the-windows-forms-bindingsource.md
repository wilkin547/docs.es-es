---
title: "Cómo: Enlazar a un servicio Web mediante el componente BindingSource de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a647f688f0ae8566a7129982e78e3d9503bee6af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="b397a-102">Cómo: Enlazar a un servicio Web mediante el componente BindingSource de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b397a-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="b397a-103">Si quiere enlazar un control de Windows Forms a los resultados obtenidos de la llamada a un servicio Web XML, puede usar un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b397a-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="b397a-104">Este procedimiento es similar a enlazar un componente <xref:System.Windows.Forms.BindingSource> a un tipo.</span><span class="sxs-lookup"><span data-stu-id="b397a-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="b397a-105">Debe crear un proxy de cliente que contenga los métodos y los tipos expuestos por el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="b397a-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="b397a-106">El proxy de cliente se genera desde el propio servicio Web (.asmx) o desde su archivo de lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="b397a-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="b397a-107">Además, el proxy de cliente debe exponer los campos de tipos complejos usados por el servicio Web como propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="b397a-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="b397a-108">Después, enlace el <xref:System.Windows.Forms.BindingSource> a uno de los tipos expuestos en el proxy de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="b397a-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="b397a-109">Para crear y enlazar a un proxy de cliente</span><span class="sxs-lookup"><span data-stu-id="b397a-109">To create and bind to a client-side proxy</span></span>  
  
1.  <span data-ttu-id="b397a-110">Cree Windows Form en el directorio que elija, con un espacio de nombres adecuado.</span><span class="sxs-lookup"><span data-stu-id="b397a-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2.  <span data-ttu-id="b397a-111">Agregue un componente <xref:System.Windows.Forms.BindingSource> al formulario.</span><span class="sxs-lookup"><span data-stu-id="b397a-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3.  <span data-ttu-id="b397a-112">Abra el símbolo del sistema de [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] y vaya al mismo directorio donde se encuentra el formulario.</span><span class="sxs-lookup"><span data-stu-id="b397a-112">Open the [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4.  <span data-ttu-id="b397a-113">En la herramienta WSDL, escriba `wsdl` y la dirección URL del archivo .asmx o WSDL del servicio web, seguido por el espacio de nombres de la aplicación y, opcionalmente, el lenguaje con el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="b397a-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="b397a-114">En el ejemplo de código siguiente se usa el servicio web situado en http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx.</span><span class="sxs-lookup"><span data-stu-id="b397a-114">The following code example uses the Web service located at http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx.</span></span> <span data-ttu-id="b397a-115">Por ejemplo, para C# escriba `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, o para Visual Basic escriba `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span><span class="sxs-lookup"><span data-stu-id="b397a-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="b397a-116">Al pasar la ruta de acceso como un argumento a la herramienta WSDL, se generará un proxy de cliente en el mismo directorio y espacio de nombres que la aplicación, en el lenguaje especificado.</span><span class="sxs-lookup"><span data-stu-id="b397a-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="b397a-117">Si usa [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], agregue el archivo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b397a-117">If you are using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], add the file to your project.</span></span>  
  
5.  <span data-ttu-id="b397a-118">En el proxy de cliente, seleccione el tipo al que se enlazará.</span><span class="sxs-lookup"><span data-stu-id="b397a-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="b397a-119">Suele ser un tipo devuelto por un método proporcionado por el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="b397a-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="b397a-120">Los campos del tipo elegido se deben exponer como propiedades públicas con fines de enlace.</span><span class="sxs-lookup"><span data-stu-id="b397a-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  <span data-ttu-id="b397a-121">Establezca la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> del <xref:System.Windows.Forms.BindingSource> en el tipo que quiera que esté contenido en el proxy de cliente del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="b397a-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="b397a-122">Para enlazar controles al BindingSource que está enlazado a un servicio Web</span><span class="sxs-lookup"><span data-stu-id="b397a-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
-   <span data-ttu-id="b397a-123">Enlace controles al <xref:System.Windows.Forms.BindingSource>, pasando como parámetro la propiedad pública del tipo de servicio Web que desee.</span><span class="sxs-lookup"><span data-stu-id="b397a-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="b397a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b397a-124">Example</span></span>  
 <span data-ttu-id="b397a-125">En el ejemplo de código siguiente se muestra cómo enlazar un componente <xref:System.Windows.Forms.BindingSource> a un servicio Web y, después, cómo enlazar un cuadro de texto al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b397a-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="b397a-126">Al hacer clic en el botón, se llama a un método de servicio Web y el resultado se mostrarán en `textbox1`.</span><span class="sxs-lookup"><span data-stu-id="b397a-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b397a-127">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b397a-127">Compiling the Code</span></span>  
 <span data-ttu-id="b397a-128">Este es un ejemplo completo que incluye un método `Main` y una versión reducida del código del proxy de cliente.</span><span class="sxs-lookup"><span data-stu-id="b397a-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="b397a-129">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b397a-129">This example requires:</span></span>  
  
-   <span data-ttu-id="b397a-130">Referencias a los ensamblados System, System.Drawing, System.Web.Services, System.Windows.Forms y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="b397a-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="b397a-131">Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b397a-131">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b397a-132">También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b397a-132">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="b397a-133">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b397a-133">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b397a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b397a-134">See Also</span></span>  
 [<span data-ttu-id="b397a-135">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="b397a-135">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="b397a-136">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="b397a-136">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
