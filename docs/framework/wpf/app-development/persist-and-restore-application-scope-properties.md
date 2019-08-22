---
title: Filtrar Conservar y restaurar propiedades en el ámbito de aplicación a través de sesiones de aplicación
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
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666723"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="476ef-102">Filtrar Conservar y restaurar propiedades en el ámbito de aplicación a través de sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="476ef-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="476ef-103">En este ejemplo se muestra cómo conservar las propiedades del ámbito de la aplicación cuando una aplicación se cierra y cómo restaurar las propiedades del ámbito de la aplicación cuando se inicia una aplicación.</span><span class="sxs-lookup"><span data-stu-id="476ef-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="476ef-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="476ef-104">Example</span></span>  
 <span data-ttu-id="476ef-105">La aplicación conserva las propiedades de ámbito de aplicación en, y las restaura desde el almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="476ef-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="476ef-106">El almacenamiento aislado es un área de almacenamiento protegido que las aplicaciones sin permiso de acceso a archivos pueden usar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="476ef-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="476ef-107">El archivo *app. Xaml* define el `App_Startup` método como el controlador para el <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento y <xref:System.Windows.Application.Exit?displayProperty=nameWithType> el `App_Exit` método como el controlador del evento, como se muestra en las líneas resaltadas del primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="476ef-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="476ef-108">En el segundo ejemplo se muestra una parte de los archivos *app.Xaml.CS* y *app. Xaml. VB* que resalta el `App_Startup` código para el método, que restaura las propiedades de ámbito de aplicación `App_Exit` y el método, que guarda el ámbito de aplicación. propiedades.</span><span class="sxs-lookup"><span data-stu-id="476ef-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
