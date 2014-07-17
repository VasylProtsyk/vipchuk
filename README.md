vipchuk
=======
<html>
<head>
    <title>Drag adn drop</title>
    <link rel="stylesheet" type="text/css" href="style.css">
    <script src="scripts.js"></script>
    <script>
        function hide_but(){
            <?php
            try{
                $user ='root';
                $pass ='';
                $db = new PDO('mysql:host=localhost;dbname=15;charset=utf8', $user, $pass);
                $db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
                $db->exec("set names utf8");
                $numbers=$db->query("SELECT cell FROM t1");

                $q = array();
                $i = 0;

                foreach($numbers as $row){
                $q[$i] = $row["cell"];
                $i++;
                }

            }
            catch (PDOException $e){
                echo($e->getMessage());
            }


            for($j = 0; $j < 16; ++$j){
                if($q[$j] == 0){
                $empty = $j+1;
                break;}
            }
            $i = 0;
            ?>

            var but =<?php echo($empty)?>;
            var eTable = document.getElementsByClassName("th");
            var count = Number(eTable.length);

            for (var i = 0; i < eTable.length; ++i) {
                if(eTable[i].getAttribute('id')== but){

                    var child = eTable[i].childNodes[1];
                    eTable[i].removeChild(child);
                    eTable[i].setAttribute('free','true');
                    break;
                }
            }
        }
</script>
</head>

<body onload="hide_but()">

<div class="main">
    <div class="text">
        <h2>15</h2>
    </div>
    <div class="save">
        <input type="button" id="ajax_save" value="Save" onclick="saveButton()">
    </div>
    <div class="buttons" >
        <table id="table">
            <tr id="tr">
                <td class="th"  id="1" free="false"  ondragenter="dragEnter(event)" ondrop="dropImg(event,this)" ondragover="makeDroppable(event)">
                    <button id="b1"  draggable="true" ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="2" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b2" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="3" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b3" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="4" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b4" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
            </tr>
            <tr id="tr">
                <td class="th" id="5" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b5" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="6" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b6" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="7" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b7" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="8" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b8" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
            </tr>
            <tr id="tr">
                <td class="th" id="9" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button  id="b9" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="10" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b10" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="11" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b11" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="12" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b12" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
            </tr>
            <tr id="tr">
                <td class="th" id="13" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b13" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="14" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b14" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="15" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b15" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
                <td class="th" id="16" free="false" ondragenter="dragEnter(event)" ondrop="dropImg(event)" ondragover="makeDroppable(event)">
                    <button id="b16" draggable="true"  ondragstart="dragImg(event)" ondragover="makeDroppable(event)"><?php echo $q[$i];$i++; ?></button>
                </td>
            </tr>
        </table>
    </div>
</div>
</body>
</html>
