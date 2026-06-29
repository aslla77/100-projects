# Rule: 보안

- 보안 문제를 추측으로 단정하지 않는다. 코드에서 확인한 사실과 가능성 있는 리스크를 구분한다.
- 공식 문서·OWASP·벤더 보안 문서·CVE·NVD를 우선한다. 커뮤니티 글은 단서로만.
- 비밀키·토큰·API 키를 코드·문서·로그에 노출하지 않는다.
- 입력값 검증은 신뢰 경계(외부 입력)에서 수행한다.
- Tier 2 이상은 `security/threat-model.md`와 `security/dependency-review.md` 필수.
- 보안 변경은 사람 승인 후 진행한다. 심각한 취약점은 release blocker로 처리한다.

## References
- OWASP: https://owasp.org/
- NVD: https://nvd.nist.gov/
- `reference-policy.md`
