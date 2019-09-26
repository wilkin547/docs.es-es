---
title: Procedimiento para admitir la interoperabilidad COM al mostrar formularios Windows Forms en sus propios subprocesos
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 41af4d81995a0a4eac912ecce7dc70cf04f012cd
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306387"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a>Procedimiento Compatibilidad con la interoperabilidad COM mostrando cada Windows Forms en su propio subproceso

Puede resolver problemas de interoperabilidad COM mostrando el formulario en un bucle de mensajes .NET Framework, que puede crear mediante el <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> método.

Para que un Windows Form funcione correctamente con una aplicación cliente COM, debe ejecutar el formulario en un bucle de mensajes de Windows Forms. Para ello, siga uno de estos procedimientos:

- Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el Windows Form. Para obtener más información, vea [Cómo: Compatibilidad con la interoperabilidad COM al mostrar Windows Forms](com-interop-by-displaying-a-windows-form-shadow.md)con el método ShowDialog.

- Muestre cada Windows Form en un subproceso independiente.

Hay una amplia compatibilidad para esta característica en Visual Studio.

Consulte [también Tutorial: Compatibilidad con la interoperabilidad COM al mostrar cada Windows Forms en su propio subproceso](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se ilustra cómo mostrar el formulario en un subproceso independiente y cómo llamar al método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> para iniciar un bombeo de mensajes de Windows Forms en ese subproceso. Para usar este enfoque, debe calcular las referencias de las llamadas al formulario desde la aplicación no administrada usando el método <xref:System.Windows.Forms.Control.Invoke%2A> .

Este enfoque requiere que cada instancia de un formulario se ejecuta en su propio subproceso usando su propio bucle de mensajes. No puede tener más de un bucle de mensajes en ejecución por subproceso. Por lo tanto, no puede cambiar el bucle de mensajes de la aplicación cliente. Sin embargo, puede modificar el componente de .NET Framework para iniciar un nuevo subproceso que use su propio bucle de mensajes.

[!code-vb[System.Windows.Forms.ComInterop#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]

[!code-vb[System.Windows.Forms.ComInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]

[!code-vb[System.Windows.Forms.ComInterop#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]

## <a name="compile-the-code"></a>Compilar el código

Compile los tipos `COMForm`, `Form1`y `FormManager` en un ensamblado llamado `COMWinform.dll`. Registre el ensamblado para la interoperabilidad COM usando uno de los métodos descritos en [Packaging an Assembly for COM](../../interop/packaging-an-assembly-for-com.md). Ahora puede usar el ensamblado y el archivo de biblioteca de tipos (.tlb) correspondiente en las aplicaciones no administradas. Por ejemplo, puede usar la biblioteca de tipos como una referencia en un proyecto ejecutable de Visual Basic 6.0.

## <a name="see-also"></a>Vea también

- [Exponer componentes de .NET Framework en COM](../../interop/exposing-dotnet-components-to-com.md)
- [Empaquetar un ensamblado para COM](../../interop/packaging-an-assembly-for-com.md)
- [Registrar ensamblados con COM](../../interop/registering-assemblies-with-com.md)
- [Cómo: Compatibilidad con la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md)
- [Información general sobre formularios Windows Forms y aplicaciones no administradas](windows-forms-and-unmanaged-applications-overview.md)
