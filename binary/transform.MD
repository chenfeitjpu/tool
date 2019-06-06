# 进制间转换 #
## 十进制转二进制 ##
```
/**
 * 十进制转二进制
 * @param int $decimal 数字
 * @return string
 */
public function decimalToBinary($decimal) {
	$prefix = 0;
	if($decimal < 0) {
		$prefix = 1;
		$decimal = -$decimal;
	}
	$result = '';
	while ($decimal) {
		$result = ($decimal & 1) . $result;
		$decimal = $decimal >> 1;
	}
	return $prefix . str_repeat('0', PHP_INT_SIZE * 8 - strlen($result) - 1) . $result;
}
```