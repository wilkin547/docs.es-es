---
title: Código fuente de L2DBForm.xaml.cs
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921159"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="c5dad-102">Código fuente de L2DBForm.xaml.cs</span><span class="sxs-lookup"><span data-stu-id="c5dad-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="c5dad-103">Esta página contiene el contenido y la descripción del C# código fuente en el archivo *L2DBForm.Xaml.CS*.</span><span class="sxs-lookup"><span data-stu-id="c5dad-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="c5dad-104">La clase parcial L2XDBForm contenida en este archivo se puede dividir en tres secciones lógicas: miembros de datos y los controladores de eventos Click de botones `OnRemove` y `OnAddBook`.</span><span class="sxs-lookup"><span data-stu-id="c5dad-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="c5dad-105">Miembros de datos</span><span class="sxs-lookup"><span data-stu-id="c5dad-105">Data members</span></span>

<span data-ttu-id="c5dad-106">Se utilizan dos miembros de datos privados para asociar esta clase con los recursos de la ventana que se utilizan en *L2DBForm.xaml*.</span><span class="sxs-lookup"><span data-stu-id="c5dad-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="c5dad-107">La variable del espacio de nombres `myBooks` se inicializa en `"http://www.mybooks.com"`.</span><span class="sxs-lookup"><span data-stu-id="c5dad-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="c5dad-108">El miembro `bookList` se inicializa en el constructor en la cadena CDATA de *L2DBForm.xaml* con la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="c5dad-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="c5dad-109">Controlador de eventos OnAddBook</span><span class="sxs-lookup"><span data-stu-id="c5dad-109">OnAddBook event handler</span></span>

<span data-ttu-id="c5dad-110">Este método contiene las siguientes tres instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c5dad-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="c5dad-111">La primera instrucción condicional se utiliza para la validación de entrada.</span><span class="sxs-lookup"><span data-stu-id="c5dad-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="c5dad-112">La segunda instrucción crea un nuevo <xref:System.Xml.Linq.XElement> a partir de los valores de cadena que el usuario ha especificado en la sección de la interfaz de usuario (IU) **Agregar nuevo libro**.</span><span class="sxs-lookup"><span data-stu-id="c5dad-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="c5dad-113">La última instrucción agrega este nuevo elemento de libro al proveedor de datos de *L2DBForm.xaml*.</span><span class="sxs-lookup"><span data-stu-id="c5dad-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="c5dad-114">En consecuencia, el enlace de datos dinámicos actualizará la IU con este nuevo elemento; no se requiere ningún código adicional proporcionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c5dad-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="c5dad-115">Controlador de eventos OnRemove</span><span class="sxs-lookup"><span data-stu-id="c5dad-115">OnRemove event handler</span></span>

<span data-ttu-id="c5dad-116">El controlador `OnRemove` es más complicado que el controlador `OnAddBook` por dos motivos.</span><span class="sxs-lookup"><span data-stu-id="c5dad-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="c5dad-117">En primer lugar, como el XML sin formato contiene espacios en blanco conservados, las nuevas líneas coincidentes deben quitarse con la entrada del libro.</span><span class="sxs-lookup"><span data-stu-id="c5dad-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="c5dad-118">En segundo lugar, por comodidad, la selección, que se hizo en el elemento eliminado, se restablece a la selección previa de la lista.</span><span class="sxs-lookup"><span data-stu-id="c5dad-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="c5dad-119">Pero el trabajo principal de quitar el elemento de libro seleccionado se logra con solo dos instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c5dad-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="c5dad-120">En primer lugar, se recupera el elemento de libro asociado con el elemento seleccionado actualmente en el cuadro de lista:</span><span class="sxs-lookup"><span data-stu-id="c5dad-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="c5dad-121">A continuación, se elimina este elemento del proveedor de datos:</span><span class="sxs-lookup"><span data-stu-id="c5dad-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="c5dad-122">De nuevo, el enlace de datos dinámicos garantiza que la IU del programa se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c5dad-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="c5dad-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5dad-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="c5dad-124">Código</span><span class="sxs-lookup"><span data-stu-id="c5dad-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="c5dad-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5dad-125">Comments</span></span>

<span data-ttu-id="c5dad-126">Para conocer el código fuente XAML asociado para esos controladores, vea [Código fuente de L2DBForm.xaml](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="c5dad-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c5dad-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5dad-127">See also</span></span>

- [<span data-ttu-id="c5dad-128">Tutorial: Ejemplo de LinqToXmlDataBinding</span><span class="sxs-lookup"><span data-stu-id="c5dad-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="c5dad-129">Código fuente de L2DBForm.xaml</span><span class="sxs-lookup"><span data-stu-id="c5dad-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)
