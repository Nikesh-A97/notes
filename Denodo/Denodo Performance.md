## Intro & Benchmarks

![[Pasted image 20230927091011.png]]
- The key idea is to do the bulk of the processing locally at the source
![[Pasted image 20230927091222.png]]
![[Pasted image 20230927091637.png]]
![[Pasted image 20230927091701.png]]
![[Pasted image 20230927091734.png]]
- Even though processing is frontloaded at the source layer, the performance impact at the source is low
- However if there are a lot of end users, the performance impact at the source may be high, limits may be imposed to prevent overloading the source DBs
	- Example, imposing a limit such as prevent a full SELECT query from a table

## Performance Optimization Techniques
![[Pasted image 20230927093104.png]]

### Query Re-writing and Delegation
![[Pasted image 20230927093345.png]]
- An example would be if you had 3 tables A, B, C in data sources D1, D1, D2. You would join A with B first then join with C.
![[Pasted image 20230927094238.png]]
![[Pasted image 20230927094419.png]]
![[Pasted image 20230927094747.png]]
![[Pasted image 20230927094918.png]]
![[Pasted image 20230927095243.png]]
![[Pasted image 20230927095321.png]]
![[Pasted image 20230927095655.png]]
![[Pasted image 20230927100034.png]]
![[Pasted image 20230927100103.png]]
![[Pasted image 20230927100416.png]]
#### Example - Use Case
![[Pasted image 20230927100823.png]]
![[Pasted image 20230927101005.png]]
![[Pasted image 20230927101249.png]]
- Until the end of the process, we won't know the final queries sent to the source
![[Pasted image 20230927101534.png]]
![[Pasted image 20230927101559.png]]
### Caching
![[Pasted image 20230927110038.png]]
![[Pasted image 20230927110531.png]]
![[Pasted image 20230927110555.png]]
![[Pasted image 20230927110607.png]]
![[Pasted image 20230927111337.png]]
- Not good for aggregate information, good for a few select fields
![[Pasted image 20230927111732.png]]
### Smart Queries

![[Pasted image 20230927112555.png]]
![[Pasted image 20230927113236.png]]
![[Pasted image 20230927113335.png]]
### MPP Execution
![[Pasted image 20230927114513.png]]
![[Pasted image 20230927114932.png]]
![[Pasted image 20230927115344.png]]
![[Pasted image 20230927115357.png]]










