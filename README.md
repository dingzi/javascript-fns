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

***

	/**
	 * 比较两个版本号
	 */
	function compareVersion(version1, version2, separator) {
		if(typeof separator === 'undefined') {separator = '.';}
		var arr1 = version1.split(separator),
			arr2 = version2.split(separator);
	
		for(var i = 0, len = arr1.length > arr2.length ? arr1.length : arr2.length; i < len; i++) {
			var val1 = parseInt(arr1[i], 10) || 0,
				val2 = parseInt(arr2[i], 10) || 0;
			if(val1 > val2) {
				return '第一个大'
			} else if(val1 < val2) {
				return '第二个大';
			}
		}
		return '两个一样大';
	}

***
	
	/**
	* 数组的洗牌算法
	* arr {Array} 传入一个数组
	* return {Array} 返回经过洗牌的数组
	 */
	function shuffleArray(arr) {
		for(var i = 0, len = arr.length; i < 1; i++) {
			var rnd = Math.floor(Math.random() * len),
				temp = arr[rnd];
			arr[rnd] = arr[i];
			arr[i] = temp;
		}
		return arr;
	}