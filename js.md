### 10.10
#### ������������
	String,Number,Null,undefined,Boolean���л����������� 		Objectһ�������������� 
#### ת���ַ� "\"
 	alert("hello world!");
	\" ��ʾ "
	\n ����
	\t �Ʊ��
	alert("\\");
	\\ ���һ��\
### 10.11
#### ��ʶ��
	1����ʶ���������֡���ĸ��_��$
	2�����������ֿ�ͷ
	3�������ǹؼ��ֺͱ�����
	4��һ�����շ�������
#### Number
	1.7976931348623157e+308  Number.MAX_VALUE	
	5e-324 			 Number.MIN_VALUE 
	���numberֵ���������ֵ ��᷵��Infinity ��ʾ������
	Infinity��NaN��typeof������������Number
#### Null
	ʹ��typeof���nullֵ����object
	ʹ��typeof���undefined����undefined
#### ǿ������ת��
	1������Number��Boolean���Ե���toString()
	null��undefinedû��toString()
	���ǿ�����String()����ֱ��ת��Ϊ�ַ���
	2���ַ���ת��Ϊ����
	(1) �ַ�����ֻ����������ֱ��ת��Ϊ����
	(2) �ַ����к��з�������ת��ΪNaN
	(3) �ַ���Ϊ����ת��Ϊ0
	3������ֵת��Ϊ����
	true->1
	false->0
	4��Nullת��Ϊ����
	null->0
	5��undefinedת��Ϊ����
	undefined->NaN
