---
title: ArrayList
categories: [java]
comments: true
---

```java
package chapter4;

import java.util.ArrayList;

public class Passenger {
	private String name;
	private String tel;
	private String seat;
		
	public Passenger (String name, String tel, String seat) {
		this.name = name;
		this.tel = tel;
		this.seat = seat;
	}

	public void setName(String name) {
		this.name = name;
	}

	public String getName() {
		return name;
	}

	public String getTel() {
		return tel;
	}

	public String getSeat() {
		return seat;
	}

	public void setTel(String tel) {
		this.tel = tel;
	}

	public void setSeat(String seat) {
		this.seat = seat;
	}

	@Override
	public String toString() {
		return "이름 = " + name + ", 연락처 = " + tel + ", 좌석 = " + seat.toString();
	}
}
```

```java
package chapter4;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class Ex3 {

	public static void main(String[] args) {
		Passenger passenger1 = new Passenger("또식이", "010-1234-1234", "이코노미");
		Passenger passenger2 = new Passenger("또식이1", "010-4321-4321", "퍼스트");
		Passenger passenger3 = new Passenger("또식이2", "010-4365-4535", "비지니스");
		Passenger passenger4 = new Passenger("또식이3", "010-7894-7894", "퍼스트");
		Passenger passenger5 = new Passenger("또식이4", "010-4654-6456", "이코노미");
		
		List<Passenger> passengerList = new ArrayList<>();
		passengerList.add(0, passenger1);
		passengerList.add(1, passenger2);
		passengerList.add(2, passenger3);
		passengerList.add(3, passenger4);
		passengerList.add(4, passenger5);
		
		Passenger passenger6 = new Passenger ("또식이5", "010-5466-5465", "이코노미");
		
		passengerList.add(0, passenger6);
		passengerList.remove(1);
		
		System.out.println(passengerList);
		System.out.println();
		
		Passenger passenger = passengerList.get(2);
		System.out.println(passenger.getName());
		System.out.println(passenger.getTel());
		System.out.println(passenger.getSeat());
		
		passenger = passengerList.get(3);
		System.out.println(passenger.getName());
		System.out.println(passenger.getTel());
		System.out.println(passenger.getSeat());
		System.out.println();
		
		System.out.println(passengerList.isEmpty()); // ←비어있는지 확인해주는 메서드, 비어있으면 true
		
		System.out.println(passengerList.size()); // ← 컬렉션 프레임워크에 들어있는 데이터의 개수를 반환
		
		for (int i = 0; i < passengerList.size(); i++) {
			System.out.println(passengerList.get(i));
		}
		
		// 향상된 for문/foreach문
		for (Passenger p : passengerList) {
			System.out.println(p);
		}
		
		Iterator<Passenger> it = passengerList.iterator();
		while(it.hasNext()) {
			Passenger p1 = it.next();
			System.out.println(p1.getName());
			System.out.println(p1.getTel());
			System.out.println(p1.getSeat());
			System.out.println();
		}
	}
}
```
