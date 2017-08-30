# WebApiDemo

## How to using
open an another project that coult be Empty Mvc than add a new controller in Controllers folder named HomeController its reason route
default
thank add a view for Index without _layout page and paste in body's div

            <label>Kategori Adı : </label>
            <input type="text" id="txtName" /> <br /><br />
            <label>Kategori Açıklaması : </label>
            <input type="text" id="txtDesc" /> <br /><br />
            <button id="btnAdd">Ekle</button>


and after html tags open scripts and paste

<script>
$("#btnAdd").click(function () {
        var cat = new Object();
        cat.KategoriAdi = $("#txtName").val();
        cat.Aciklama = $("#txtDesc").val();

        $.ajax({
            type: "post",
            dataType: "json",
            data: cat,
            url: "http://localhost:58539/api/Category/AddCategory",
            success: function (result) {
                if (result == "basarili") {
                    alert("eklendi");
                }
            }
        })
    })
</script>

you need install Jquery and referance to html page.. 

all types must be same named with your api project's ViewModel class properties like KategoriAdi,Aciklama and if return Json('basarili')
ofcource here same too like result == 'basarili'


