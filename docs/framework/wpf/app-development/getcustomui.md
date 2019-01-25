---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 012590a21ac24b1146c30405c9872355a4b50802
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627257"
---
# <a name="getcustomui"></a>GetCustomUI
Lo llama PresentationHost.exe para obtener mensajes de error y progreso personalizado desde el host, si se implementa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzProgressAssemblyName`  
  
 [out] Un puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.  
  
 `pwzProgressClassName`  
  
 [out] El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferiblemente un [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] de archivos con <xref:System.Windows.Controls.Page> es su elemento de nivel superior. Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Un puntero al ensamblado que contiene la interfaz de usuario de error proporcionado por el host.  
  
 `pwzErrorClassName`  
  
 [out] El nombre de la clase que es el usuario de error proporcionado por el host de la interfaz, preferiblemente un archivo XAML con <xref:System.Windows.Controls.Page> es su elemento de nivel superior. Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: ignorado.  
  
## <a name="remarks"></a>Comentarios  
 Una aplicación host puede tener un tema concreto que es posible que no cumplen interfaces de usuario predeterminada del PresentationHost.exe. Si este es el caso, puede implementar la aplicación host [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) para devolver las interfaces de usuario de progreso y error a PresentationHost.exe. PresentationHost.exe siempre llamará [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) antes de usar sus interfaces de usuario de forma predeterminada.  
  
 Esta función se llama una vez durante la inicialización de PresentationHost.  
  
## <a name="see-also"></a>Vea también
- [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
