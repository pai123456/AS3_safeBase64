# AS3_safeBase64

以"-_"替换"+/"，并去掉了"=="，可以安全地在url中传输。
用法：
```
var str:String = "Base64Safe"
var b2:String = Base64Safe.encodeSafe(convertStringToByteArray(str));
var deb2:ByteArray = Base64Safe.decodeSafe(b2);
trace(convertByteArrayToString(deb2));

//字符串转化为二进制数组
public static function convertStringToByteArray(str:String):ByteArray
{
  var bytes:ByteArray;
  if (str)
  {
    bytes = new ByteArray();
    bytes.writeUTFBytes(str);
  }
  return bytes;
}
//ByteArray转String
public static function convertByteArrayToString(bytes:ByteArray):String
{
  var str:String;
  if (bytes)
  {
    bytes.position = 0;
    str = bytes.readUTFBytes(bytes.length);
  }

  return str;
}
```
