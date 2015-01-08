# javascript-fns



	/**
 	* 格式化一个数字为指定位数 eg:1 => '001'
	 * num   {Number/String} 需要格式化的数字
	 * digit {Number}        需要将数字格式化的位数
	 * return {String}
	 */
	function parseNumber(num, digit) {
		num = num.toString();
		var len = num.toString().length;
		if(len < digit) {
			var diff = digit - len,
				prefix = '';
			while(diff) {
				prefix += '0';
				diff--;
			}
			return prefix + num;
		}
		return num;
	}