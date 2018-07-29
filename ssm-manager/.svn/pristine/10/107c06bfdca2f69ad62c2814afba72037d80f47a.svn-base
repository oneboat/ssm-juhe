package com.learn.service.impl;

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import com.learn.mapper.TbItemMapper;
import com.learn.pojo.TbItem;
import com.learn.pojo.TbItemExample;
import com.learn.pojo.TbItemExample.Criteria;
import com.learn.service.ItemService;
@Service
public class ItemServiceImpl implements ItemService {
	
	@Autowired
	private TbItemMapper itemMapper;
	
	public TbItem getItemById(long itemId) {
		//方式一：根据主键查询
		//TbItem tbItem = itemMapper.selectByPrimaryKey(itemId);
		//方式二：根据条件查询,创建对象
		TbItemExample example = new TbItemExample();
		//创建条件
		Criteria criteria = example.createCriteria();
		criteria.andIdEqualTo(itemId);//条件与这个id相等
		//执行查询
		List<TbItem> list = itemMapper.selectByExample(example);
		if (list!=null &&list.size()>0) {
			return list.get(0);
		}
		return null;
	}

}
