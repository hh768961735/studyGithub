###  const��let
	function getClothing(isCold) {
 		 if (isCold) {
    			var freezing = 'Grab a jacket!';
  		} else {
   		 	var hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}

	����getClothing(false),����̨���undefined����Ϊ����������ǰ��
	freezing������������û�и�ֵ���������undefined,����var��ȱ�㡣

	function getClothing(isCold) {
 		 if (isCold) {
    			const freezing = 'Grab a jacket!';
  		} else {
   		 	const hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}
	����getClothing(false),����̨������Ϊfreezing����else�������У�
	û�б�������const��let���ᱻ������ǰ��
	+ let���������������¸�ֵ�����ǲ�����ͬһ����������������(����������ֱ�Ӹ�ֵ)
	+ const�����ı��������ʼ����������ͬһ�����������������¸�ֵ