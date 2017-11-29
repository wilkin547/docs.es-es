---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a>GetCustomUI
Lo llama PresentationHost.exe obtener personalizados de progreso y mensajes de error desde el host, si implementa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzProgressAssemblyName`  
  
 [out] Un puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.  
  
 `pwzProgressClassName`  
  
 [out] El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferiblemente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] de archivos con <xref:System.Windows.Controls.Page> es su elemento de nivel superior. Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Un puntero al ensamblado que contiene la interfaz de usuario de error proporcionado por el host.  
  
 `pwzErrorClassName`  
  
 [out] El nombre de la clase que es el usuario de error proporcionado por el host de la interfaz, preferentemente un archivo XAML con <xref:System.Windows.Controls.Page> es su elemento de nivel superior. Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: pasa por alto.  
  
## <a name="remarks"></a>Comentarios  
 Una aplicación host puede tener un tema específico que interfaces de usuario predeterminadas del PresentationHost.exe no pueden cumplir. Si este es el caso, puede implementar la aplicación host [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) para devolver las interfaces de usuario de progreso y error a PresentationHost.exe. PresentationHost.exe siempre llamará [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) antes de utilizar sus interfaces de usuario de forma predeterminada.  
  
 Esta función se invoca una vez durante la inicialización de PresentationHost.  
  
## <a name="see-also"></a>Vea también  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
