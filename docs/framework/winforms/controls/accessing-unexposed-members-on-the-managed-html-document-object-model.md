---
title: Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 1de8afcd7167406f10c4d541e95a0fa68be16611
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658957"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="caee8-102">Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="caee8-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="caee8-103">Administrado HTML Document Object Model (DOM) contiene una clase denominada <xref:System.Windows.Forms.HtmlElement> que expone las propiedades, métodos y eventos que sean comunes a todos los elementos HTML.</span><span class="sxs-lookup"><span data-stu-id="caee8-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="caee8-104">A veces, sin embargo, necesitará tener acceso a miembros que no exponen directamente a la interfaz administrada.</span><span class="sxs-lookup"><span data-stu-id="caee8-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="caee8-105">En este tema se describen dos formas para tener acceso a miembros no expuestos, así como [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] y funciones de VBScript definidas dentro de una página Web.</span><span class="sxs-lookup"><span data-stu-id="caee8-105">This topic examines two ways for accessing unexposed members, including [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="caee8-106">Acceso a miembros no expuestos a través de Interfaces administradas</span><span class="sxs-lookup"><span data-stu-id="caee8-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="caee8-107"><xref:System.Windows.Forms.HtmlDocument> y <xref:System.Windows.Forms.HtmlElement> proporcionan cuatro métodos que permiten el acceso a miembros no expuestos.</span><span class="sxs-lookup"><span data-stu-id="caee8-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="caee8-108">En la tabla siguiente se muestra los tipos y sus métodos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="caee8-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="caee8-109">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="caee8-109">Member Type</span></span>|<span data-ttu-id="caee8-110">Método (s)</span><span class="sxs-lookup"><span data-stu-id="caee8-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="caee8-111">Propiedades (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="caee8-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="caee8-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="caee8-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="caee8-113">Eventos (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="caee8-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="caee8-114">Eventos (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="caee8-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="caee8-115">Eventos (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="caee8-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="caee8-116">Al usar estos métodos, se supone que tiene un elemento del tipo subyacente correcto.</span><span class="sxs-lookup"><span data-stu-id="caee8-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="caee8-117">Suponga que desea escuchar el `Submit` eventos de un `FORM` página de elemento en un elemento HTML, por lo que puede realizar algún procesamiento previo en el `FORM`de valores antes de que el usuario los envíe al servidor.</span><span class="sxs-lookup"><span data-stu-id="caee8-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="caee8-118">Lo ideal es que, si tiene control sobre la HTML, definiría la `FORM` para tener un único `ID` atributo.</span><span class="sxs-lookup"><span data-stu-id="caee8-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="caee8-119">Después de cargar esta página en el <xref:System.Windows.Forms.WebBrowser> control, puede usar el <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> método para recuperar el `FORM` en tiempo de ejecución mediante `form1` como argumento.</span><span class="sxs-lookup"><span data-stu-id="caee8-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="caee8-120">Obtener acceso a las Interfaces no administradas</span><span class="sxs-lookup"><span data-stu-id="caee8-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="caee8-121">También puede tener acceso a miembros no expuestos en el DOM HTML administrado mediante el uso de las interfaces no administradas de modelo de objetos componentes (COM) expuestas por cada clase de DOM.</span><span class="sxs-lookup"><span data-stu-id="caee8-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="caee8-122">Esto se recomienda si tiene que realizar varias llamadas a miembros no expuestos, o si estos miembros devuelven otras interfaces no administradas no encapsuladas por administrado HTML DOM.</span><span class="sxs-lookup"><span data-stu-id="caee8-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="caee8-123">La tabla siguiente muestran todas las interfaces no administradas que se exponen a través de HTML DOM. administrado</span><span class="sxs-lookup"><span data-stu-id="caee8-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="caee8-124">Haga clic en cada vínculo para obtener una explicación de su uso y, por ejemplo, el código.</span><span class="sxs-lookup"><span data-stu-id="caee8-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="caee8-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="caee8-125">Type</span></span>|<span data-ttu-id="caee8-126">Interfaz no administrada</span><span class="sxs-lookup"><span data-stu-id="caee8-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="caee8-127">La manera más fácil de usar las interfaces COM es agregar una referencia a la biblioteca no administrada de DOM de HTML (MSHTML.dll) desde su aplicación, aunque esto no se admite.</span><span class="sxs-lookup"><span data-stu-id="caee8-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="caee8-128">Para obtener más información, consulte [934368 del artículo de Knowledge Base](https://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="caee8-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="caee8-129">Obtener acceso a las funciones de Script</span><span class="sxs-lookup"><span data-stu-id="caee8-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="caee8-130">Una página HTML puede definir una o varias funciones mediante un lenguaje de scripting, como [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript.</span><span class="sxs-lookup"><span data-stu-id="caee8-130">An HTML page can define one or more functions by using a scripting language such as [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] or VBScript.</span></span> <span data-ttu-id="caee8-131">Estas funciones se colocan dentro de un `SCRIPT` página en la página y se pueden ejecutar a petición o en respuesta a un evento en el DOM.</span><span class="sxs-lookup"><span data-stu-id="caee8-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="caee8-132">Puede llamar a cualquier funciones de secuencia de comandos que se definen en una página HTML mediante la <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> método.</span><span class="sxs-lookup"><span data-stu-id="caee8-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="caee8-133">Si el método de script devuelve un elemento HTML, puede usar una conversión de tipos para convertir este resultado devuelto para un <xref:System.Windows.Forms.HtmlElement>.</span><span class="sxs-lookup"><span data-stu-id="caee8-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="caee8-134">Para obtener información detallada y código de ejemplo, vea <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span><span class="sxs-lookup"><span data-stu-id="caee8-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caee8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="caee8-135">See also</span></span>
- [<span data-ttu-id="caee8-136">Utilizar el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="caee8-136">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
