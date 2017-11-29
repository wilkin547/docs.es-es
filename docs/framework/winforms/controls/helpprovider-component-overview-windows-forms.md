---
title: "Información general sobre el componente HelpProvider (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42a788e44fde80662748e19a7244ce77bb26118f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="6f79e-102">Información general sobre el componente HelpProvider (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6f79e-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="6f79e-103">Los formularios Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) componente se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm, generado con HTML Help Workshop o un archivo .htm) con la aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="6f79e-103">The Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="6f79e-104">Puede proporcionar ayuda en una variedad de formas:</span><span class="sxs-lookup"><span data-stu-id="6f79e-104">You can provide help in a variety of ways:</span></span>  
  
-   <span data-ttu-id="6f79e-105">Proporcionar ayuda contextual para los controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f79e-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
-   <span data-ttu-id="6f79e-106">Proporcionar ayuda contextual en un cuadro de diálogo determinado o controles específicos en un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6f79e-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
-   <span data-ttu-id="6f79e-107">Abra un archivo de ayuda en áreas específicas, como la página principal de una tabla de contenido, el índice o una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6f79e-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="6f79e-108">Mediante el proveedor de ayuda</span><span class="sxs-lookup"><span data-stu-id="6f79e-108">Using the Help Provider</span></span>  
 <span data-ttu-id="6f79e-109">Agregar un <xref:System.Windows.Forms.HelpProvider> componente al formulario Windows Forms permite a los demás controles en el formulario para exponer las propiedades de la Ayuda de la <xref:System.Windows.Forms.HelpProvider> componente.</span><span class="sxs-lookup"><span data-stu-id="6f79e-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="6f79e-110">Esto le permite proporcionar ayuda para los controles del formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f79e-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="6f79e-111">Puede asociar un archivo de ayuda con la <xref:System.Windows.Forms.HelpProvider> componente mediante el <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6f79e-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="6f79e-112">Especificar el tipo de ayuda proporcionada mediante una llamada a <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> y proporcionar un valor comprendido entre el <xref:System.Windows.Forms.HelpNavigator> enumeración para el control especificado.</span><span class="sxs-lookup"><span data-stu-id="6f79e-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="6f79e-113">Proporcionar la palabra clave o el tema de ayuda mediante una llamada a la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6f79e-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="6f79e-114">Si lo desea, para asociar una cadena de ayuda específica a otro control, use la <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6f79e-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="6f79e-115">La cadena que se asocia a un control con este método se muestra en una ventana emergente cuando el usuario presiona la tecla F1 mientras el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6f79e-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="6f79e-116">Si <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> no se ha establecido, debe usar <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> para proporcionar el texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="6f79e-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="6f79e-117">Si ha establecido tanto <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> y la cadena de ayuda, Ayuda basada en <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="6f79e-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f79e-118">Puede encontrar problemas con la ruta de acceso relativa al especificando la ruta de acceso al archivo de ayuda en la <xref:System.Windows.Forms.Help.ShowHelp%2A> método o <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> propiedad de la <xref:System.Windows.Forms.HelpProvider> control.</span><span class="sxs-lookup"><span data-stu-id="6f79e-118">You may encounter problems using the relative path when specifiying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="6f79e-119">Por lo tanto, asegúrese de usar la ruta de acceso absoluta del archivo para especificar el archivo de ayuda.</span><span class="sxs-lookup"><span data-stu-id="6f79e-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f79e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f79e-120">See Also</span></span>  
 [<span data-ttu-id="6f79e-121">Sistemas de ayuda en aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f79e-121">Help Systems in Windows Forms Applications</span></span>](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
