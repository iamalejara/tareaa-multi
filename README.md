<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "https://www.w3.org/TR/html4/loose.dtd">
<html>
    <head>
        <title>Suma, resta, multiplicación, división o residuo</title>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    </head>
    <body>
<?php

if ($_SERVER['REQUEST_METHOD']=='POST')
{
    $a = intval ($_POST['a']);
    $b = intval ($_POST['b']);
    $operacion = intval ($_POST['operacion']);
    $resultado_final=0;
    if($operacion==1)
    {
        $resultado_final=$a+$b;
        echo 'Suma<br>'
    }
    if($operacion==2)
    {
        $resultado_final=$a-$b;
        echo 'Resta<br>'
    }
    if($operacion==3)
    {
        $resultado_final=$a*$b;
        echo 'Multiplicaci&oacute;n<br>'
    }
    if($operacion==4&&$b==0)
        echo 'No se puede obtener la divisi&oacute;n<br>'
    if($operacion==4&&$b!=0)
    {
        $resultado_final=$a/$b;
        echo 'Divisi&oacute;n<br>'
    }
    if($operacion==5&&$b==0)
        echo 'No se puede obtener el residuo<br>'
    if($operacion==5&&$b!=0)
    {
        $resultado_final=$a%$b;
        echo 'Residuo<br>'
    }
    echo 'Valor de resultado final: ' . $resultado_final . "<br/>\n";
}
 
?>
        <form method="post">
            <table style="text-align: left; margin-left: auto; margin-right: auto;" border="1" cellpadding="1" cellspacing="1">
                <tbody>
                    <tr>
                        <td>
                            <label for="a">Ingresa el valor de a:</label>
                        </td>
                        <td>
                            <input name="a" required="required" step="1" type="number" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <label for="b">Ingresa el valor de b:</label>
                        </td>
                        <td>
                            <input name="b" required="required" step="1" type="number" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <label for="operacion">Selecciona el valor de operacion:</label>
                        </td>
                        <td>
                            <select name="operacion" required="required">
                                <option value="1">Suma</option>
                                <option value="2">Resta</option>
                                <option value="3">Multiplicaci&oacute;n</option>
                                <option value="4">Divisi&oacute;n</option>
                                <option value="5">Residuo</option>
                            </select>
                        </td>
                    </tr>
                    <tr align="center">
                        <td colspan="2" rowspan="1">
                            <input value="Procesar" type="submit" />
                        </td>
                    </tr>
                </tbody>
            </table>
        </form>
    </body>
</html>
