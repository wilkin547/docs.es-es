---
title: "Cómo: Proporcionar ayuda en una aplicación para Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d23e5d5d19e17aedd37d4d5f6cbc41429463ddfb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="5ee02-102">Cómo: Proporcionar ayuda en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="5ee02-102">How to: Provide Help in a Windows Application</span></span>
<span data-ttu-id="5ee02-103">Puede usar de la <xref:System.Windows.Forms.HelpProvider> componente para asociar los temas de ayuda dentro de un archivo de ayuda a controles específicos en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5ee02-103">You can use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="5ee02-104">El archivo de ayuda puede ser HTML, HTMLHelp 1.x o superior.</span><span class="sxs-lookup"><span data-stu-id="5ee02-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ee02-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="5ee02-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5ee02-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="5ee02-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5ee02-107">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5ee02-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-provide-help"></a><span data-ttu-id="5ee02-108">Para proporcionar ayuda</span><span class="sxs-lookup"><span data-stu-id="5ee02-108">To provide Help</span></span>  
  
1.  <span data-ttu-id="5ee02-109">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.HelpProvider> al formulario.</span><span class="sxs-lookup"><span data-stu-id="5ee02-109">From the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>  
  
     <span data-ttu-id="5ee02-110">El componente estará en la bandeja, en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5ee02-110">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="5ee02-111">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad al archivo de ayuda .chm, .col o. htm.</span><span class="sxs-lookup"><span data-stu-id="5ee02-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>  
  
3.  <span data-ttu-id="5ee02-112">Seleccione otro control tiene en el formulario y, en la **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5ee02-112">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>  
  
     <span data-ttu-id="5ee02-113">Se trata de la cadena que se pasa a través de la <xref:System.Windows.Forms.HelpProvider> componente al archivo de ayuda para abrir el tema de Ayuda apropiado.</span><span class="sxs-lookup"><span data-stu-id="5ee02-113">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>  
  
4.  <span data-ttu-id="5ee02-114">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> en un valor de la <xref:System.Windows.Forms.HelpNavigator> enumeración.</span><span class="sxs-lookup"><span data-stu-id="5ee02-114">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>  
  
     <span data-ttu-id="5ee02-115">Esto determina la forma en la que la propiedad **HelpKeyword** pasa al sistema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="5ee02-115">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="5ee02-116">La siguiente tabla muestra los valores posibles y sus descripciones.</span><span class="sxs-lookup"><span data-stu-id="5ee02-116">The following table shows the possible settings and their descriptions.</span></span>  
  
    |<span data-ttu-id="5ee02-117">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="5ee02-117">Member Name</span></span>|<span data-ttu-id="5ee02-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ee02-118">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="5ee02-119">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="5ee02-119">AssociateIndex</span></span>|<span data-ttu-id="5ee02-120">Especifica que el índice de un tema determinado se realiza en la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="5ee02-120">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|  
    |<span data-ttu-id="5ee02-121">Find</span><span class="sxs-lookup"><span data-stu-id="5ee02-121">Find</span></span>|<span data-ttu-id="5ee02-122">Especifica que se muestre la página de búsqueda de una dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="5ee02-122">Specifies that the search page of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="5ee02-123">Índice</span><span class="sxs-lookup"><span data-stu-id="5ee02-123">Index</span></span>|<span data-ttu-id="5ee02-124">Especifica que se muestre el índice de una dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="5ee02-124">Specifies that the index of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="5ee02-125">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="5ee02-125">KeywordIndex</span></span>|<span data-ttu-id="5ee02-126">Especifica una palabra clave que buscar y la acción que se realizará en la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="5ee02-126">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|  
    |<span data-ttu-id="5ee02-127">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="5ee02-127">TableOfContents</span></span>|<span data-ttu-id="5ee02-128">Especifica que se muestra la tabla de contenidos del archivo de ayuda HTML 1.0.</span><span class="sxs-lookup"><span data-stu-id="5ee02-128">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|  
    |<span data-ttu-id="5ee02-129">Tema</span><span class="sxs-lookup"><span data-stu-id="5ee02-129">Topic</span></span>|<span data-ttu-id="5ee02-130">Especifica que se muestra el tema al que hace referencia la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="5ee02-130">Specifies that the topic referenced by the specified URL is displayed.</span></span>|  
  
 <span data-ttu-id="5ee02-131">En tiempo de ejecución, al presionar F1 cuando el control, para que ha establecido la **HelpKeyword** y **HelpNavigator** propiedades: tiene foco abrirá el archivo de ayuda asociados a ese <xref:System.Windows.Forms.HelpProvider> componente.</span><span class="sxs-lookup"><span data-stu-id="5ee02-131">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>  
  
 <span data-ttu-id="5ee02-132">Actualmente, la propiedad **HelpNamespace** admite archivos de ayuda en los tres formatos siguientes: HTMLHelp 1.x, HTMLHelp 2.0 y HTML.</span><span class="sxs-lookup"><span data-stu-id="5ee02-132">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="5ee02-133">Por lo tanto, puede establecer la propiedad **HelpNamespace** en una dirección http://, como una página web.</span><span class="sxs-lookup"><span data-stu-id="5ee02-133">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="5ee02-134">Si esto sucede, se abrirá el explorador predeterminado en la página web con la cadena especificada en la propiedad **HelpKeyword** utilizada como delimitador.</span><span class="sxs-lookup"><span data-stu-id="5ee02-134">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="5ee02-135">El delimitador se utiliza para saltar a una parte específica de una página HTML.</span><span class="sxs-lookup"><span data-stu-id="5ee02-135">The anchor is used to jump to a specific part of an HTML page.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ee02-136">Tenga cuidado de comprobar cualquier información que se envíe desde un cliente antes de utilizarla en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5ee02-136">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="5ee02-137">Los usuarios malintencionados podrían intentar enviar o inyectar scripts ejecutables, instrucciones SQL u otro código.</span><span class="sxs-lookup"><span data-stu-id="5ee02-137">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="5ee02-138">Antes de mostrar la entrada del usuario, almacénela en una base de datos o trabaje con ella, y compruebe que no contiene información potencialmente insegura.</span><span class="sxs-lookup"><span data-stu-id="5ee02-138">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="5ee02-139">Una forma habitual de comprobación es utilizar una expresión regular para buscar palabras clave como "SCRIPT" cuando se recibe la entrada de un usuario.</span><span class="sxs-lookup"><span data-stu-id="5ee02-139">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>  
  
 <span data-ttu-id="5ee02-140">También puede usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar Ayuda emergente, aunque se haya configurado para mostrar archivos de ayuda para los controles en los formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5ee02-140">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="5ee02-141">Para más información, consulte [Cómo: Mostrar ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="5ee02-141">For more information, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee02-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ee02-142">See Also</span></span>  
 [<span data-ttu-id="5ee02-143">Mostrar ayuda emergente</span><span class="sxs-lookup"><span data-stu-id="5ee02-143">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [<span data-ttu-id="5ee02-144">Controlar la ayuda mediante componentes Tooltip</span><span class="sxs-lookup"><span data-stu-id="5ee02-144">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="5ee02-145">Integrar la Ayuda de usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ee02-145">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="5ee02-146">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ee02-146">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
