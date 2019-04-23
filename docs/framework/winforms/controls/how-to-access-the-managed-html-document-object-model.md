---
title: Procedimiento para obtener acceso a Document Object Model HTML administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 04d5f9e6f128d9b4ed3f07a5faebe06ae4ffdebf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315197"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="91bcc-102">Procedimiento para obtener acceso a Document Object Model HTML administrado</span><span class="sxs-lookup"><span data-stu-id="91bcc-102">How to: Access the Managed HTML Document Object Model</span></span>
<span data-ttu-id="91bcc-103">Puede acceder al Document Object Model (DOM) HTML administrado desde dos tipos de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="91bcc-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
-   <span data-ttu-id="91bcc-104">Una aplicación de A Windows Forms (.exe) que hospedó el control <xref:System.Windows.Forms.WebBrowser> administrado.</span><span class="sxs-lookup"><span data-stu-id="91bcc-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="91bcc-105">Estas dos tecnologías se complementan entre sí; el control <xref:System.Windows.Forms.WebBrowser> muestra la página al usuario y el DOM HTML representa la estructura lógica del documento.</span><span class="sxs-lookup"><span data-stu-id="91bcc-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
-   <span data-ttu-id="91bcc-106">Un <xref:System.Windows.Forms.UserControl> de Windows Forms hospedado en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="91bcc-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="91bcc-107">Puede acceder al DOM HTML representando la página en la que su <xref:System.Windows.Forms.UserControl> está hospedado para cambiar la estructura del documento o abrir cuadros de diálogo modales, entre otras posibilidades.</span><span class="sxs-lookup"><span data-stu-id="91bcc-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="91bcc-108">Para acceder al DOM desde una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91bcc-108">To access DOM from a Windows Forms application</span></span>  
  
1. <span data-ttu-id="91bcc-109">Hospede un control <xref:System.Windows.Forms.WebBrowser> en su aplicación de Windows Forms y supervise el evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.</span><span class="sxs-lookup"><span data-stu-id="91bcc-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="91bcc-110">Para obtener información detallada sobre cómo hospedar controles y supervisar eventos, consulte [Eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="91bcc-110">For details on hosting controls and monitoring for events, see [Events](../../../standard/events/index.md).</span></span>  
  
2. <span data-ttu-id="91bcc-111">Recupere el <xref:System.Windows.Forms.HtmlDocument> de la página actual; para ello, acceda a la propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A> del control <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="91bcc-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="91bcc-112">Para acceder al DOM desde un UserControl hospedado en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="91bcc-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1. <span data-ttu-id="91bcc-113">Cree su propia clase derivada personalizada de la clase <xref:System.Windows.Forms.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="91bcc-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="91bcc-114">Para obtener más información, vea [Cómo: Crear controles compuestos](how-to-author-composite-controls.md).</span><span class="sxs-lookup"><span data-stu-id="91bcc-114">For more information, see [How to: Author Composite Controls](how-to-author-composite-controls.md).</span></span>  
  
2. <span data-ttu-id="91bcc-115">Coloque el código siguiente dentro del controlador de evento Load para su <xref:System.Windows.Forms.UserControl>:</span><span class="sxs-lookup"><span data-stu-id="91bcc-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="91bcc-116">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="91bcc-116">Robust Programming</span></span>  
  
1. <span data-ttu-id="91bcc-117">Cuando use DOM en el control <xref:System.Windows.Forms.WebBrowser>, debe esperar siempre hasta que se produzca el evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> antes de intentar acceder a la propiedad <xref:System.Windows.Forms.WebBrowser.Document%2A> del control <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="91bcc-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="91bcc-118">El evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> se genera una vez cargado todo el documento; si usa el DOM antes, corre el riesgo de provocar una excepción en tiempo de ejecución en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="91bcc-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="91bcc-119">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="91bcc-119">.NET Framework Security</span></span>  
  
1. <span data-ttu-id="91bcc-120">Su aplicación o <xref:System.Windows.Forms.UserControl> requerirá confianza completa para poder acceder al DOM HTML administrado.</span><span class="sxs-lookup"><span data-stu-id="91bcc-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="91bcc-121">Si está implementando una aplicación de Windows Forms mediante [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], puede solicitar confianza completa usando la elevación de permisos o una implementación de aplicación de confianza; consulte [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="91bcc-121">If you are deploying a Windows Forms application using [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91bcc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="91bcc-122">See also</span></span>

- [<span data-ttu-id="91bcc-123">Utilizar el Modelo de objetos de documento HTML administrado</span><span class="sxs-lookup"><span data-stu-id="91bcc-123">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
