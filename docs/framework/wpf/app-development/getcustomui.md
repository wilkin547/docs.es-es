---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005711"
---
# <a name="getcustomui"></a>GetCustomUI
Lo llama PresentationHost. exe para obtener los mensajes de error y de progreso personalizados del host, si se implementan.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzProgressAssemblyName`  
  
 enuncia Puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.  
  
 `pwzProgressClassName`  
  
 enuncia El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferiblemente un archivo XAML con <xref:System.Windows.Controls.Page> es su elemento de nivel superior. Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 enuncia Puntero al ensamblado que contiene la interfaz de usuario de error proporcionada por el host.  
  
 `pwzErrorClassName`  
  
 enuncia El nombre de la clase que es la interfaz de usuario de error proporcionada por el host, preferiblemente un archivo XAML con <xref:System.Windows.Controls.Page> es el elemento de nivel superior. Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: ignorado.  
  
## <a name="remarks"></a>Comentarios  
 Una aplicación host puede tener un tema específico del que es posible que las interfaces de usuario predeterminadas de PresentationHost. exe no se ajusten a. En este caso, la aplicación host puede implementar [GetCustomUI](getcustomui.md) para devolver interfaces de usuario de progreso y error a PresentationHost. exe. PresentationHost. exe siempre llama a [GetCustomUI](getcustomui.md) antes de usar sus interfaces de usuario predeterminadas.  
  
 Esta función se llama una vez durante la inicialización de PresentationHost.  
  
## <a name="see-also"></a>Vea también

- [IWpfHostSupport](iwpfhostsupport.md)
