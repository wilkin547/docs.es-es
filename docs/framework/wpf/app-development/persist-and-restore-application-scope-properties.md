---
title: Procedimiento Conservar y restaurar propiedades en el ámbito de aplicación a través de sesiones de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: 99b04060d4e7c14313655010dc4fbd5ce1c90487
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977657"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="def63-102">Procedimiento Conservar y restaurar propiedades en el ámbito de aplicación a través de sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="def63-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="def63-103">En este ejemplo se muestra cómo conservar las propiedades del ámbito de la aplicación cuando se cierra una aplicación, y cómo restaurar las propiedades de ámbito de la aplicación cuando una aplicación es el siguiente inicio.</span><span class="sxs-lookup"><span data-stu-id="def63-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="def63-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="def63-104">Example</span></span>  
 <span data-ttu-id="def63-105">La aplicación conserva las propiedades del ámbito de aplicación y restaura desde el almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="def63-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="def63-106">Almacenamiento aislado es un área de almacenamiento protegido que puede usarse con seguridad aplicaciones sin permiso de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="def63-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="def63-107">El *App.xaml* archivo define la `App_Startup` método como controlador para el <xref:System.Windows.Application.Startup?displayProperty=nameWithType> eventos y el `App_Exit` método como controlador para el <xref:System.Windows.Application.Exit?displayProperty=nameWithType> eventos, como se muestra en las líneas resaltadas del primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="def63-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="def63-108">El segundo ejemplo muestra una parte de la *App.xaml.cs* y *App.xaml.vb* archivos que resalta el código para el `App_Startup` método, que restaura las propiedades de ámbito de la aplicación y el `App_Exit` método, que guarda las propiedades de ámbito de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="def63-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
