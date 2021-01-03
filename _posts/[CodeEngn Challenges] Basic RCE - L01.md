# Basic RCE - L01

``` 
HDD를 CD-Rom으로 인식시키기 위해서는 GetDriveTypeA의 리턴값이 무엇이 되어야 하는가
```



실행 시, 아래와 같은 메시지를 확인 할 수 있다. 

![](\post_img\post1_1.png)



GetDriveTypeA이 CD-Rom을 인식했을 경우, '5'를 리턴한다. 리턴값을 변경하면 아래와 같은 메시지를 확인 할 수 있다. 

![](\post_img\post1_4.png)



## GetDriveTypeA

``` c++
UINT GetDriveTypeA(
  LPCSTR lpRootPathName
);
```

`lpRootPathName` : 드라이브의 루트 디렉터리



| 반환 코드 / 값 | 기술 |
| :------------- | ---- |
| DRIVE_UNKNOWN / 0 | 드라이브 유형을 확인할 수 없다. |
| DRIVE_NO_ROOT_DIR / 1 | 루트 경로가 잘못되었다. ex) 지정된 경로에 마운트 된 볼륨이 없음 |
| DRIVE_REMOVABLE / 2 | 드라이브에 이동식 미디어가 있다. ex) 플로피 드라이브, Thumb 드라이브, 플래시 카드 리더 |
| DRIVE_FIXED / 3 | 드라이브에 고정 미디어가 있습니다. ex) 하드 디스크 드라이브, 플래시 드라이브 |
| DRIVE_REMOTE / 4 | 드라이브가 원격 (네트워크) 드라이브이다. |
| DRIVE_CDROM / 5 | 드라이브가 CD-ROM 드라이브이다. |
| DRIVE_RAMDISK / 6 | 드라이브는 RAM 디스크이다. |

