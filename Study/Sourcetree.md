\* clone : 원격 저장소 복사  
\* 현재 branch / head branch  

\* commit내용 작성 요령  
  : 요약 한줄 작성 → 한줄 띄움 → 자세한 내용 작성  

\* 이전 commit으로 되돌리기  
  : "코드뭉치 버리기"  
  : "checkout"  
  
\* merge  
  : 최종 master branch로 합치는 과정  

\* reset후, 다른 내용 작성 후, push  
  + 강제 push 또는 터미널에서 `$ git push --force`  
  + 병합(merge) 후 push  
  + brach를 만들어서 되돌림  
  
\* revert로 되돌리기
  : "커밋 되돌리기"  
  : 또다시 되돌리려면 "초기화 -> hard"  
  : 내용은 바껴도 commit은 남길 수 있다 but 충돌 나기 쉽다  
  
  
  + 여러개 되돌릴때는 최신부터 순서대로 rever반복 (하나 revert한 상태에서 다른 요소 revert)  
  + 터미널에 작성 `$ git revert HEAD HEAD~1` HEAD~1은 부모요소
  + 터미널 빠져나가기 `ESC` → `:WQ`
