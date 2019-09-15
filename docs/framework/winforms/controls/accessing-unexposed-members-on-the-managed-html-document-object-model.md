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
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988400"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="acebb-102">Acceso a miembros no expuestos en el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="acebb-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="acebb-103">El Document Object Model HTML administrado (dom) contiene una clase denominada <xref:System.Windows.Forms.HtmlElement> que expone las propiedades, los métodos y los eventos que tienen todos los elementos HTML en común.</span><span class="sxs-lookup"><span data-stu-id="acebb-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="acebb-104">Sin embargo, a veces necesitará tener acceso a los miembros que la interfaz administrada no expone directamente.</span><span class="sxs-lookup"><span data-stu-id="acebb-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="acebb-105">En este tema se examinan dos formas de obtener acceso a miembros no expuestos, incluidas las funciones de JScript y VBScript definidas dentro de una página web.</span><span class="sxs-lookup"><span data-stu-id="acebb-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="acebb-106">Obtener acceso a miembros no expuestos a través de interfaces administradas</span><span class="sxs-lookup"><span data-stu-id="acebb-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="acebb-107"><xref:System.Windows.Forms.HtmlDocument>y <xref:System.Windows.Forms.HtmlElement> proporcionan cuatro métodos que permiten el acceso a miembros no expuestos.</span><span class="sxs-lookup"><span data-stu-id="acebb-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="acebb-108">En la tabla siguiente se muestran los tipos y sus métodos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="acebb-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="acebb-109">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="acebb-109">Member Type</span></span>|<span data-ttu-id="acebb-110">Método (s)</span><span class="sxs-lookup"><span data-stu-id="acebb-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="acebb-111">Propiedades (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="acebb-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="acebb-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="acebb-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="acebb-113">Eventos (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="acebb-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="acebb-114">Eventos (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="acebb-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="acebb-115">Eventos (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="acebb-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="acebb-116">Cuando se usan estos métodos, se supone que tiene un elemento del tipo subyacente correcto.</span><span class="sxs-lookup"><span data-stu-id="acebb-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="acebb-117">Supongamos que desea escuchar el `Submit` evento de un `FORM` elemento en una página HTML, de modo que pueda realizar algún procesamiento previo de los `FORM`valores de antes de que el usuario los envíe al servidor.</span><span class="sxs-lookup"><span data-stu-id="acebb-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="acebb-118">Idealmente, si tiene control sobre el código HTML, definiría `FORM` para tener un atributo único. `ID`</span><span class="sxs-lookup"><span data-stu-id="acebb-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```html  
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
  
 <span data-ttu-id="acebb-119">Después de cargar esta página en el <xref:System.Windows.Forms.WebBrowser> control, puede usar el <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> método para recuperar `FORM` en tiempo de ejecución utilizando `form1` como argumento.</span><span class="sxs-lookup"><span data-stu-id="acebb-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="acebb-120">Acceso a interfaces no administradas</span><span class="sxs-lookup"><span data-stu-id="acebb-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="acebb-121">También puede tener acceso a miembros no expuestos en el DOM HTML administrado mediante las interfaces del modelo de objetos componentes (COM) no administradas expuestas por cada clase DOM.</span><span class="sxs-lookup"><span data-stu-id="acebb-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="acebb-122">Esto se recomienda si tiene que realizar varias llamadas a miembros no expuestos, o si los miembros no expuestos devuelven otras interfaces no administradas no encapsuladas por el DOM HTML administrado.</span><span class="sxs-lookup"><span data-stu-id="acebb-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="acebb-123">En la tabla siguiente se muestran todas las interfaces no administradas que se exponen a través del DOM HTML administrado.</span><span class="sxs-lookup"><span data-stu-id="acebb-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="acebb-124">Haga clic en cada vínculo para obtener una explicación de su uso y el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="acebb-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="acebb-125">Type</span><span class="sxs-lookup"><span data-stu-id="acebb-125">Type</span></span>|<span data-ttu-id="acebb-126">Interfaz no administrada</span><span class="sxs-lookup"><span data-stu-id="acebb-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="acebb-127">La manera más sencilla de utilizar las interfaces COM es agregar una referencia a la biblioteca DOM HTML no administrada (MSHTML. dll) de la aplicación, aunque no se admite.</span><span class="sxs-lookup"><span data-stu-id="acebb-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="acebb-128">Para obtener más información, vea el [artículo 934368 de Knowledge Base](https://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="acebb-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="acebb-129">Obtener acceso a funciones de script</span><span class="sxs-lookup"><span data-stu-id="acebb-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="acebb-130">Una página HTML puede definir una o varias funciones mediante un lenguaje de scripting como JScript o VBScript.</span><span class="sxs-lookup"><span data-stu-id="acebb-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="acebb-131">Estas funciones se colocan dentro `SCRIPT` de una página de la página y se pueden ejecutar a petición o como respuesta a un evento en el Dom.</span><span class="sxs-lookup"><span data-stu-id="acebb-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="acebb-132">Puede llamar a cualquier función de script que defina en una página HTML mediante <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> el método.</span><span class="sxs-lookup"><span data-stu-id="acebb-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="acebb-133">Si el método de script devuelve un elemento HTML, puede usar una conversión para convertir el resultado devuelto en <xref:System.Windows.Forms.HtmlElement>.</span><span class="sxs-lookup"><span data-stu-id="acebb-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="acebb-134">Para obtener más información y código de <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>ejemplo, vea.</span><span class="sxs-lookup"><span data-stu-id="acebb-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acebb-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="acebb-135">See also</span></span>

- [<span data-ttu-id="acebb-136">Utilizar el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="acebb-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
