---
title: 'Cambio importante: objetos de WinForms no accesibles desde código nativo'
description: Obtenga información sobre el cambio importante en .NET 5, donde los objetos de Windows Forms ya no son accesibles desde código nativo.
ms.date: 01/29/2021
ms.openlocfilehash: 823d37cb8115b8669b254878325a350809393e79
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256101"
---
# <a name="native-code-cant-access-windows-forms-objects"></a>El código nativo no puede acceder a objetos Windows Forms.

A partir de .NET 5, ya no puede tener acceso a objetos de Windows Forms desde código nativo.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, algunos tipos de Windows Forms se representaban como visibles para la interoperabilidad COM y, por tanto, se podía tener acceso al código nativo. A partir de .NET 5, no hay ninguna API de Windows Forms visible para la interoperabilidad COM o accesible para el código nativo. El entorno de ejecución de .NET ya no admite la creación de bibliotecas de tipos personalizados directamente. Además, el entorno de ejecución de .NET no puede depender de la biblioteca de tipos para .NET Framework (lo que requeriría mantener la forma de las clases tal como estaban en .NET Framework).

## <a name="reason-for-change"></a>Motivo del cambio

- Eliminación de `ComVisible(true)` de las enumeraciones que se usaron para la generación y búsqueda de la biblioteca de tipos (archivo TLB): como no hay ningún TLB de WinForms proporcionado por .NET Core, no hay ningún valor para mantener este atributo.
- Eliminación de `ComVisible(true)` de las clases `AccessibleObject`: las clases no son "CoCreateable" (no tienen ningún constructor sin parámetros), y la exposición de una instancia ya existente a COM no requiere ese atributo.
- Eliminación de `ComVisible(true)` de las clases `Control` y `Component`: esto se usaba para permitir el hospedaje de controles de WinForms a través de OLE/ActiveX, por ejemplo en VB6 o MFC. Sin embargo, requiere un TLB para WinForms, que ya no se proporciona, así como la activación basada en el registro, que tampoco funcionaría de forma integrada. Por lo general, no se ha realizado el mantenimiento del hospedaje basado en COM de los controles de WinForms, por lo que se ha quitado la compatibilidad en lugar de dejarla en un estado no admitido.
- Eliminación de atributos `ClassInterface` de los controles: si no se admite el hospedaje a través de OLE/ActiveX, estos atributos ya no son necesarios. Se mantienen en otros lugares en los que los objetos todavía están expuestos a COM y el atributo puede ser pertinente.
- Eliminación de `ComVisible(true)` de `EventArgs`: se usaban con más probabilidad con el hospedaje de OLE/ActiveX, que ya no se admite. Tampoco son "CoCreateable", por lo que el atributo no tiene ningún propósito. Además, la exposición de las instancias existentes sin proporcionar un TLB no tiene sentido.
- Eliminación de `ComVisible(true)` de delegados: se desconoce la finalidad, pero dado que ya no se admite el hospedaje de ActiveX de controles de WinForms, no es probable que tenga alguna utilidad.
- Eliminación de `ComVisible(true)` de algún código no público: el único posible consumidor sería el nuevo diseñador de Visual Studio, pero sin un GUID especificado, no es probable que siga siendo necesario.
- Eliminación de `ComVisible(true)` de algunas clases de diseñador público arbitrarias: es posible que el diseñador de Visual Studio anterior haya estado usando la interoperabilidad COM para comunicarse con estas clases. Sin embargo, el antiguo diseñador no es compatible con .NET Core, por lo que pocas personas lo necesitarían como `ComVisible`.
- `IWin32Window` definió el mismo GUID que se definió en .NET Framework, que tiene consecuencias peligrosas. Si requiere interoperabilidad con .NET Framework, utilice `ComImport`.
- El `IDataObject` administrado por WinForms se hizo `ComVisible`. Esto no es necesario, hay una declaración de interfaz de `ComImport` independiente para la interoperabilidad COM de `IDataObject`. Es contraproducente que el `IDataObject` administrado sea `ComVisible`, ya que no se proporciona ningún TLB y la serialización siempre dará error. Además, no se especificó el GUID y se diferencia de .NET Framework, por lo que es poco probable que la eliminación de un IID no documentado afecte negativamente a los clientes.
- Eliminación de `ComVisible(false)`: se colocan en lugares aparentemente arbitrarios y son redundantes cuando el valor predeterminado es no exponer clases a la interoperabilidad COM.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

El ejemplo siguiente funciona en .NET Framework y .NET Core 3.1. Este ejemplo se basa en la biblioteca de tipos de .NET Framework, que permite que el código JavaScript vuelva a llamar a la subclase del formulario mediante reflexión.

```cs
[PermissionSet(SecurityAction.Demand, Name="FullTrust")]
[System.Runtime.InteropServices.ComVisibleAttribute(true)]
public class Form1 : Form
{
    private WebBrowser webBrowser1 = new WebBrowser();

    protected override void OnLoad(EventArgs e)
    {
        webBrowser1.AllowWebBrowserDrop = false;
        webBrowser1.IsWebBrowserContextMenuEnabled = false;
        webBrowser1.WebBrowserShortcutsEnabled = false;
        webBrowser1.ObjectForScripting = this;

        webBrowser1.DocumentText =
            "<html><body><button " +
            "onclick=\"window.external.Test('called from script code')\">" +
            "call client code from script code</button>" +
            "</body></html>";
    }

    public void Test(String message)
    {
        MessageBox.Show(message, "client code");
    }
}
```

Hay dos formas posibles de hacer que el ejemplo funcione en .NET 5 y versiones posteriores:

- Introducir un objeto `ObjectForScripting` declarado por el usuario que admita `IDispatch` (que se aplica de forma predeterminada, a menos que se cambie explícitamente en el nivel de proyecto).

  ```cs
  public class MyScriptObject
  {
      private Form1 _form;

      public MyScriptObject(Form1 form)
      {
          _form = form;
      }

      public void Test(string message)
      {
          MessageBox.Show(message, "client code");
      }
  }

  public partial class Form1 : Form
  {
      protected override void OnLoad(EventArgs e)
      {
          ...

          // Works correctly.
          webBrowser1.ObjectForScripting = new MyScriptObject(this);

          ...
      }
  }
  ```

- Declarar una interfaz con los métodos que se van a exponer.

  ```cs
  public interface IForm1
  {
      void Test(string message);
  }

  [ComDefaultInterface(typeof(IForm1))]
  public partial class Form1 : Form, IForm1
  {
      protected override void OnLoad(EventArgs e)
      {
          ...

          // Works correctly.
          webBrowser1.ObjectForScripting = this;

          ...
      }
  }
  ```

## <a name="affected-apis"></a>API afectadas

Todas las API de Windows Forms.

<!--

### Category

- Windows Forms

-->
